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
description: После настройки ключа клиента Узнайте, как управлять им с помощью восстановления ключей АКВ и управления разрешениями и политиками шифрования данных.
ms.openlocfilehash: 21c1fedce1ebc09e6c33b74a1b2c035c90988e12
ms.sourcegitcommit: f80c6c52e5b08290f74baec1d64c4070046c32e4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/12/2020
ms.locfileid: "44717310"
---
# <a name="manage-customer-key"></a><span data-ttu-id="bf6a4-103">Управление ключом клиента</span><span class="sxs-lookup"><span data-stu-id="bf6a4-103">Manage Customer Key</span></span>

<span data-ttu-id="bf6a4-104">После того как вы настроили ключ клиента для Office 365, вы можете управлять ключами, как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-104">After you've set up Customer Key for Office 365, you can manage your keys as described in this article.</span></span> <span data-ttu-id="bf6a4-105">Дополнительные сведения о ключе клиента см.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-105">Learn more about Customer Key in the related topics.</span></span>

## <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="bf6a4-106">Восстановление ключей Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="bf6a4-106">Restore Azure Key Vault keys</span></span>

<span data-ttu-id="bf6a4-107">Перед выполнением восстановления используйте возможности восстановления, предоставляемые функцией обратимого удаления.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-107">Before performing a restore, use the recovery capabilities provided by soft delete.</span></span> <span data-ttu-id="bf6a4-108">Для всех ключей, используемых с ключом клиента, необходимо включить функцию обратимого удаления.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-108">All keys that are used with Customer Key are required to have soft delete enabled.</span></span> <span data-ttu-id="bf6a4-109">Обратимое удаление действует как корзина и позволяет выполнить восстановление до 90 дней без необходимости восстановления.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-109">Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore.</span></span> <span data-ttu-id="bf6a4-110">Восстановление должно требоваться только в крайних или необычных обстоятельствах, например, при потере ключа или основного хранилища ключей.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-110">Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost.</span></span> <span data-ttu-id="bf6a4-111">Если необходимо восстановить ключ для использования с ключом клиента, в Azure PowerShell запустите командлет Restore – Азурекэйваулткэй следующим образом:</span><span class="sxs-lookup"><span data-stu-id="bf6a4-111">If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

<span data-ttu-id="bf6a4-112">Пример:</span><span class="sxs-lookup"><span data-stu-id="bf6a4-112">For example:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="bf6a4-113">Если хранилище ключей уже содержит ключ с таким же именем, операция восстановления завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-113">If the key vault already contains a key with the same name, the restore operation fails.</span></span> <span data-ttu-id="bf6a4-114">Restore — Азкэйваулткэй восстанавливает все ключевые версии и все метаданные для ключа, включая имя ключа.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-114">Restore-AzKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
## <a name="manage-key-vault-permissions"></a><span data-ttu-id="bf6a4-115">Управление разрешениями для хранилища ключей</span><span class="sxs-lookup"><span data-stu-id="bf6a4-115">Manage key vault permissions</span></span>

<span data-ttu-id="bf6a4-116">Доступно несколько командлетов, которые позволяют просматривать и при необходимости удалять разрешения для хранилища ключей.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-116">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions.</span></span> <span data-ttu-id="bf6a4-117">Возможно, вам потребуется удалить разрешения, например, когда сотрудник покидает команду.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-117">You might need to remove permissions, for example, when an employee leaves the team.</span></span> <span data-ttu-id="bf6a4-118">Для каждой из этих задач вы будете использовать Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-118">For each of these tasks, you will use Azure PowerShell.</span></span> <span data-ttu-id="bf6a4-119">Сведения о Azure PowerShell можно найти в статье [Обзор Azure PowerShell](https://docs.microsoft.com/powershell/azure/).</span><span class="sxs-lookup"><span data-stu-id="bf6a4-119">For information about Azure Powershell, see [Overview of Azure PowerShell](https://docs.microsoft.com/powershell/azure/).</span></span>

<span data-ttu-id="bf6a4-120">Чтобы просмотреть разрешения на доступ к хранилищу ключей, запустите командлет Get – Азкэйваулт.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-120">To view key vault permissions, run the Get-AzKeyVault cmdlet.</span></span>

```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="bf6a4-121">Пример:</span><span class="sxs-lookup"><span data-stu-id="bf6a4-121">For example:</span></span>

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="bf6a4-122">Чтобы удалить разрешения администратора, запустите командлет Remove – Азкэйваултакцессполици:</span><span class="sxs-lookup"><span data-stu-id="bf6a4-122">To remove an administrator's permissions, run the Remove-AzKeyVaultAccessPolicy cmdlet:</span></span>
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

<span data-ttu-id="bf6a4-123">Пример:</span><span class="sxs-lookup"><span data-stu-id="bf6a4-123">For example:</span></span>

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="manage-data-encryption-policies-deps-with-customer-key"></a><span data-ttu-id="bf6a4-124">Управление политиками шифрования данных (ДЕПС) с помощью ключа клиента</span><span class="sxs-lookup"><span data-stu-id="bf6a4-124">Manage data encryption policies (DEPs) with Customer Key</span></span>

<span data-ttu-id="bf6a4-125">Ключевые обработчики клиентов ДЕПС отличаются в разных службах.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-125">Customer Key handles DEPs differently between the different services.</span></span> <span data-ttu-id="bf6a4-126">Например, вы можете создать другое количество ДЕПС для разных служб.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-126">For example, you can create a different number of DEPs for the different services.</span></span>

<span data-ttu-id="bf6a4-127">**Exchange Online и Skype для бизнеса:** Можно создать до 50 ДЕПС.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-127">**Exchange Online and Skype for Business:** You can create up to 50 DEPs.</span></span> <span data-ttu-id="bf6a4-128">Инструкции приведены в разделе [Создание политики шифрования данных (DEP) для использования с Exchange Online и Skype для бизнеса](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business).</span><span class="sxs-lookup"><span data-stu-id="bf6a4-128">For instructions, see [Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business).</span></span>

<span data-ttu-id="bf6a4-129">**Файлы SharePoint Online, OneDrive для бизнеса и teams:** Функция DEP применяется к данным в одном географическом расположении, также называемом _географическим_.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-129">**SharePoint Online, OneDrive for Business, and Teams files:** A DEP applies to data in one geographic location, also called a _geo_.</span></span> <span data-ttu-id="bf6a4-130">Если вы используете функцию поддержки нескольких регионов в Office 365, вы можете создать одну функцию DEP для каждого географического объекта.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-130">If you use the multi-geo feature of Office 365, you can create one DEP per geo.</span></span> <span data-ttu-id="bf6a4-131">Если вы не используете поддержку нескольких регионов, вы можете создать одну функцию DEP.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-131">If you are not using multi-geo, you can create one DEP.</span></span> <span data-ttu-id="bf6a4-132">Как правило, функция DEP создается при настройке ключа клиента.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-132">Normally, you create the DEP when you set up Customer Key.</span></span> <span data-ttu-id="bf6a4-133">Инструкции, приведенные в разделе [Создание политики шифрования данных (DEP) для каждого географического региона SharePoint Online и OneDrive для бизнеса](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo).</span><span class="sxs-lookup"><span data-stu-id="bf6a4-133">For instructions, see [Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo).</span></span>

### <a name="view-the-deps-youve-created-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="bf6a4-134">Просмотр созданного ДЕПС для Exchange Online и Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="bf6a4-134">View the DEPs you've created for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="bf6a4-135">Чтобы просмотреть список всех ДЕПС, созданных для Exchange Online и Skype для бизнеса с помощью командлета Get-Dataencryptionpolicy используется PowerShell, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-135">To view a list of all the DEPs you've created for Exchange Online and Skype for Business using the Get-DataEncryptionPolicy PowerShell cmdlet, complete these steps.</span></span>

1. <span data-ttu-id="bf6a4-136">С помощью рабочей или учебной учетной записи, имеющей разрешения глобального администратора в Организации, [подключитесь к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="bf6a4-136">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

2. <span data-ttu-id="bf6a4-137">Чтобы возвратить все ДЕПС в Организации, выполните командлет Get – Dataencryptionpolicy используется без параметров.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-137">To return all DEPs in your organization, run the Get-DataEncryptionPolicy cmdlet without any parameters.</span></span>

  ```powershell
  Get-DataEncryptionPolicy
  ```

  <span data-ttu-id="bf6a4-138">Дополнительные сведения о командлете Get – Dataencryptionpolicy используется можно найти в статье [Get – dataencryptionpolicy используется](https://docs.microsoft.com/powershell/module/exchange/get-dataencryptionpolicy?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="bf6a4-138">For more information about the Get-DataEncryptionPolicy cmdlet, see [Get-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/get-dataencryptionpolicy?view=exchange-ps).</span></span>

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a><span data-ttu-id="bf6a4-139">Назначение функции DEP перед переносом почтового ящика в облако</span><span class="sxs-lookup"><span data-stu-id="bf6a4-139">Assign a DEP before you migrate a mailbox to the cloud</span></span>

<span data-ttu-id="bf6a4-140">При назначении функции DEP Microsoft 365 шифрует содержимое почтового ящика с помощью назначенной функции DEP во время миграции.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-140">When you assign the DEP, Microsoft 365 encrypts the contents of the mailbox using the assigned DEP during the migration.</span></span> <span data-ttu-id="bf6a4-141">Этот процесс является более эффективным, чем перенос почтового ящика, назначение DEP, а затем ожидание выполнения шифрования, что может занять несколько часов или, возможно, дней.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-141">This process is more efficient than migrating the mailbox, assigning the DEP, and then waiting for encryption to take place, which can take hours or possibly days.</span></span>

<span data-ttu-id="bf6a4-142">Чтобы назначить средство предотвращения выполнения данных для почтового ящика перед его переносом в Office 365, выполните командлет Set-MailUser в Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bf6a4-142">To assign a DEP to a mailbox before you migrate it to Office 365, run the Set-MailUser cmdlet in Exchange Online PowerShell:</span></span>

1. <span data-ttu-id="bf6a4-143">С помощью рабочей или учебной учетной записи, имеющей разрешения глобального администратора в Организации, [подключитесь к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="bf6a4-143">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

2. <span data-ttu-id="bf6a4-144">Выполните командлет Set – MailUser.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-144">Run the Set-MailUser cmdlet.</span></span>

  ```powershell
  Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
  ```

  <span data-ttu-id="bf6a4-145">Где *женералмаилбоксормаилусеридпараметер* указывает почтовый ящик, а *датаенкриптионполициидпараметер* — идентификатор функции DEP.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-145">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox, and *DataEncryptionPolicyIdParameter* is the ID of the DEP.</span></span> <span data-ttu-id="bf6a4-146">Дополнительные сведения о командлете Set – MailUser см. в разделе [Set – MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="bf6a4-146">For more information about the Set-MailUser cmdlet, see [Set-MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser?view=exchange-ps).</span></span>

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="bf6a4-147">Определение функции DEP, назначенной для почтового ящика</span><span class="sxs-lookup"><span data-stu-id="bf6a4-147">Determine the DEP assigned to a mailbox</span></span>

<span data-ttu-id="bf6a4-148">Чтобы определить, какая функция DEP назначена почтовому ящику, используйте командлет Get – MailboxStatistics.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-148">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet.</span></span> <span data-ttu-id="bf6a4-149">Командлет возвращает уникальный идентификатор (GUID).</span><span class="sxs-lookup"><span data-stu-id="bf6a4-149">The cmdlet returns a unique identifier (GUID).</span></span>
  
1. <span data-ttu-id="bf6a4-150">С помощью рабочей или учебной учетной записи, имеющей разрешения глобального администратора в Организации, [подключитесь к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="bf6a4-150">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   <span data-ttu-id="bf6a4-151">Где *женералмаилбоксормаилусеридпараметер* указывает почтовый ящик, а ДАТАЕНКРИПТИОНПОЛИЦИИД Возвращает GUID объекта DEP.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-151">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox and DataEncryptionPolicyID returns the GUID of the DEP.</span></span> <span data-ttu-id="bf6a4-152">Дополнительные сведения о командлете Get – MailboxStatistics можно найти в статье [Get – MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="bf6a4-152">For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics?view=exchange-ps).</span></span>
  
2. <span data-ttu-id="bf6a4-153">Выполните командлет Get-Dataencryptionpolicy используется, чтобы узнать понятное имя DEP, которому назначен почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-153">Run the Get-DataEncryptionPolicy cmdlet to find out the friendly name of the DEP to which the mailbox is assigned.</span></span>
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   <span data-ttu-id="bf6a4-154">Где *GUID* — это идентификатор GUID, возвращенный командлетом Get-MailboxStatistics на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-154">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span>

## <a name="verify-that-customer-key-has-finished-encryption"></a><span data-ttu-id="bf6a4-155">Проверка того, что ключ клиента завершил шифрование</span><span class="sxs-lookup"><span data-stu-id="bf6a4-155">Verify that Customer Key has finished encryption</span></span>

<span data-ttu-id="bf6a4-156">После того как вы выполнили откат ключа клиента, назначили новую функцию DEP или перенесли почтовый ящик, выполните действия, описанные в этом разделе, чтобы убедиться, что шифрование завершено.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-156">Whether you've just rolled a Customer Key, assigned a new DEP, or migrated a mailbox, use the steps in this section to ensure that encryption completes.</span></span>

### <a name="verify-encryption-completes-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="bf6a4-157">Проверка того, что шифрование завершено для Exchange Online и Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="bf6a4-157">Verify encryption completes for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="bf6a4-158">Шифрование почтового ящика может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-158">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="bf6a4-159">Рекомендуется подождать 72 часов, прежде чем пытаться проверить шифрование после изменения функции DEP или при первом назначении функции защиты почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-159">We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="bf6a4-160">Используйте командлет Get-MailboxStatistics, чтобы определить, зашифрован ли почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-160">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="bf6a4-161">Свойство IsFalse возвращает значение **true** , если почтовый ящик зашифрован, и значение **false** , если почтовый ящик не зашифрован.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-161">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox is not encrypted.</span></span>

<span data-ttu-id="bf6a4-162">Время на завершение перемещения почтовых ящиков зависит от размера почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-162">The time to complete mailbox moves depends on the size of the mailbox.</span></span> <span data-ttu-id="bf6a4-163">Если ключ клиента не полностью зашифровал почтовый ящик после 72 часов с момента назначения новой функции DEP, обратитесь в службу поддержки Майкрософт за помощью.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-163">If Customer Key hasn't completely encrypted the mailbox after 72 hours from the time you assign a new DEP, contact Microsoft support for help.</span></span> <span data-ttu-id="bf6a4-164">Командлет New-MoveRequest больше недоступен для перемещений локальных почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-164">The New-MoveRequest cmdlet is no longer available for local mailbox moves.</span></span> <span data-ttu-id="bf6a4-165">Для получения дополнительных сведений обратитесь к [этому уведомлению](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) .</span><span class="sxs-lookup"><span data-stu-id="bf6a4-165">Refer to [this announcement](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) for additional information.</span></span>

### <a name="verify-encryption-completes-for-sharepointonlineonedriveforbusinessandteamsfiles"></a><span data-ttu-id="bf6a4-166">Проверка того, что шифрование выполнено для SharePoint Online, OneDrive для бизнеса и файлов Teams</span><span class="sxs-lookup"><span data-stu-id="bf6a4-166">Verify encryption completes for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="bf6a4-167">Проверьте состояние шифрования, выполнив командлет Get – Сподатаенкриптионполици, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-167">Check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="bf6a4-168">Выходные данные этого командлета включают:</span><span class="sxs-lookup"><span data-stu-id="bf6a4-168">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="bf6a4-169">Универсальный код ресурса (URI) первичного ключа.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-169">The URI of the primary key.</span></span>

- <span data-ttu-id="bf6a4-170">Универсальный код ресурса (URI) вторичного ключа.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-170">The URI of the secondary key.</span></span>

- <span data-ttu-id="bf6a4-171">Состояние шифрования для Geo.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-171">The encryption status for the geo.</span></span> <span data-ttu-id="bf6a4-172">Возможные состояния:</span><span class="sxs-lookup"><span data-stu-id="bf6a4-172">Possible states include:</span></span>

  - <span data-ttu-id="bf6a4-173">**Регистрация незарегистрирована:** Шифрование ключей клиентов еще не применено.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-173">**Unregistered:** Customer Key encryption has not yet been applied.</span></span>

  - <span data-ttu-id="bf6a4-174">**Регистрация:** Шифрование ключей клиентов применено, а файлы находятся в процессе шифрования.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-174">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted.</span></span> <span data-ttu-id="bf6a4-175">Если ключ для географического проекта регистрируется, вы также увидите сведения о том, какой процент сайтов в гео завершен, чтобы можно было отслеживать ход шифрования.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-175">If the key for the geo is registering, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span>

  - <span data-ttu-id="bf6a4-176">**Зарегистрировано:** Шифрование ключей клиентов применено, а все файлы на всех сайтах зашифрованы.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-176">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span>

  - <span data-ttu-id="bf6a4-177">**Пошаговое руководство:** Выполняется основной этап.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-177">**Rolling:** A key roll is in progress.</span></span> <span data-ttu-id="bf6a4-178">Если ключ для Geo является скользящим, вы также увидите сведения о том, на каком проценте сайтов выполнялась операция полного выполнения, чтобы можно было отслеживать ход выполнения.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-178">If the key for the geo is rolling, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span>

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a><span data-ttu-id="bf6a4-179">Отзыв ключей и начало процесса очистки данных</span><span class="sxs-lookup"><span data-stu-id="bf6a4-179">Revoke your keys and start the data purge path process</span></span>

<span data-ttu-id="bf6a4-180">Вы управляете отзывами всех корневых ключей, включая ключ доступности.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-180">You control the revocation of all root keys including the availability key.</span></span> <span data-ttu-id="bf6a4-181">Ключ клиента обеспечивает управление аспектом планирования выхода нормативных требований.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-181">Customer Key provides control of the exit planning aspect of the regulatory requirements for you.</span></span> <span data-ttu-id="bf6a4-182">Если вы решили отозвать ключи для очистки данных и выйти из службы, служба удаляет ключ доступности после завершения процесса очистки данных.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-182">If you decide to revoke your keys to purge your data and exit the service, the service deletes the availability key once the data purge process completes.</span></span>

<span data-ttu-id="bf6a4-183">Microsoft 365 выполняет аудит и проверку пути очистки данных.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-183">Microsoft 365 audits and validates the data purge path.</span></span> <span data-ttu-id="bf6a4-184">Для получения дополнительных сведений посетите отчет ССАЕ 18 SOC 2, доступный на [портале доверия службы](https://servicetrust.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="bf6a4-184">For more information, see the SSAE 18 SOC 2 Report available on the [Service Trust Portal](https://servicetrust.microsoft.com/).</span></span> <span data-ttu-id="bf6a4-185">Кроме того, корпорация Майкрософт рекомендует следующие документы:</span><span class="sxs-lookup"><span data-stu-id="bf6a4-185">In addition, Microsoft recommends the following documents:</span></span>

- [<span data-ttu-id="bf6a4-186">Оценка риска и рекомендации по соответствию финансовых учреждениям в облаке Майкрософт</span><span class="sxs-lookup"><span data-stu-id="bf6a4-186">Risk Assessment and Compliance Guide for Financial Institutions in the Microsoft Cloud</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [<span data-ttu-id="bf6a4-187">Рекомендации по планированию выхода O365</span><span class="sxs-lookup"><span data-stu-id="bf6a4-187">O365 Exit Planning Considerations</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

<span data-ttu-id="bf6a4-188">Путь очистки данных слегка различается для разных служб.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-188">The data purge path differs slightly between the different services.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="bf6a4-189">Отзыв ключей клиентов и ключа доступности для Exchange Online и Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="bf6a4-189">Revoke your Customer Keys and the availability key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="bf6a4-190">Когда вы инициируете путь очистки данных для Exchange Online и Skype для бизнеса, вы настраиваете постоянный запрос на очистку данных для функции DEP.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-190">When you initiate the data purge path for Exchange Online and Skype for Business, you set a permanent data purge request on a DEP.</span></span> <span data-ttu-id="bf6a4-191">Это приведет к удалению зашифрованных данных в почтовых ящиках, к которым назначена функция DEP.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-191">Doing so permanently deletes encrypted data within the mailboxes to which that DEP is assigned.</span></span>

<span data-ttu-id="bf6a4-192">Так как командлет PowerShell можно запускать только с одним компонентом DEP, рекомендуется переназначить одну функцию DEP для всех почтовых ящиков, прежде чем инициировать путь очистки данных.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-192">Since you can only run the PowerShell cmdlet against one DEP at a time, consider reassigning a single DEP to all of your mailboxes before you initiate the data purge path.</span></span>

> [!WARNING]
> <span data-ttu-id="bf6a4-193">Не используйте путь очистки данных для удаления подмножества почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-193">Do not use the data purge path to delete a subset of your mailboxes.</span></span> <span data-ttu-id="bf6a4-194">Этот процесс предназначен только для клиентов, использующих службу.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-194">This process is only intended for customers who are exiting the service.</span></span>

<span data-ttu-id="bf6a4-195">Чтобы инициировать путь очистки данных, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-195">To initiate the data purge path, complete these steps:</span></span>

1. <span data-ttu-id="bf6a4-196">Удалите разрешения для переноса и переноса для "O365 Exchange Online" из Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-196">Remove wrap and unwrap permissions for "O365 Exchange Online" from Azure Key Vaults.</span></span>

2. <span data-ttu-id="bf6a4-197">С помощью рабочей или учебной учетной записи, имеющей права глобального администратора в Организации, [подключитесь к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="bf6a4-197">Using a work or school account that has global administrator privileges in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

3. <span data-ttu-id="bf6a4-198">Для каждого компонента DEP, содержащего почтовые ящики, которые необходимо удалить, выполните командлет [Set – dataencryptionpolicy используется](https://docs.microsoft.com/powershell/module/exchange/set-dataencryptionpolicy) следующим образом.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-198">For each DEP that contains mailboxes that you want to delete, run the [Set-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/set-dataencryptionpolicy) cmdlet as follows.</span></span>

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   <span data-ttu-id="bf6a4-199">Если команда не выполняется, убедитесь, что вы удалили разрешения Exchange Online из обоих ключей в Azure Key Vault, как указано ранее в этой задаче.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-199">If the command fails, ensure that you've removed the Exchange Online permissions from both keys in Azure Key Vault as specified earlier in this task.</span></span><span data-ttu-id="bf6a4-200">После установки переключателя параметрами permanentdatapurgerequested с помощью командлета Set – Dataencryptionpolicy используется вы больше не сможете назначать эту функцию DEP для почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-200"> Once you've set the PermanentDataPurgeRequested switch using the Set-DataEncryptionPolicy cmdlet, you'll no longer be able to assign this DEP to mailboxes.</span></span>

4. <span data-ttu-id="bf6a4-201">Обратитесь в службу поддержки Майкрософт и запросите Едокумент очистки данных.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-201">Contact Microsoft support and request the Data Purge eDocument.</span></span>

    <span data-ttu-id="bf6a4-202">По Вашему запросу корпорация Майкрософт отправляет вам юридический документ для подтверждения и авторизации удаления данных.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-202">At your request, Microsoft sends you a legal document to acknowledge and authorize data deletion.</span></span> <span data-ttu-id="bf6a4-203">Этот документ должен быть подписан сотрудником вашей организации, который зарегистрировался в качестве утверждающего в FastTrack.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-203">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="bf6a4-204">Обычно это руководитель или другой назначенный сотрудник компании, который уполномоченным пользователям подписывать документы от имени вашей организации.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-204">Normally, this is an executive or other designated person in your company who is legally authorized to sign the paperwork on behalf of your organization.</span></span>

5. <span data-ttu-id="bf6a4-205">После того как ваш представитель подписал юридический документ, верните его в корпорацию Майкрософт (обычно через подпись едок).</span><span class="sxs-lookup"><span data-stu-id="bf6a4-205">Once your representative has signed the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

    <span data-ttu-id="bf6a4-206">Когда корпорация Майкрософт получает юридический документ, корпорация Майкрософт запускает командлеты для запуска очистки данных, которая сначала удаляет политику, помечает почтовые ящики для постоянных удалений, а затем удаляет ключ доступности.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-206">Once Microsoft receives the legal document, Microsoft runs cmdlets to trigger the data purge which first deletes the policy, marks the mailboxes for permanent deletion, then deletes the availability key.</span></span> <span data-ttu-id="bf6a4-207">После завершения процесса очистки данных данные очищаются, недоступны для Exchange Online и не могут быть восстановлены.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-207">Once the data purge process completes, the data has been purged, is inaccessible to Exchange Online, and is not recoverable.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepointonlineonedriveforbusinessandteamsfiles"></a><span data-ttu-id="bf6a4-208">Отзыв ключей клиентов и ключа доступности для файлов SharePoint Online, OneDrive для бизнеса и Teams</span><span class="sxs-lookup"><span data-stu-id="bf6a4-208">Revoke your Customer Keys and the availability key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="bf6a4-209">Чтобы инициировать путь очистки данных для SharePoint Online, OneDrive для бизнеса и файлов Teams, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-209">To initiate the data purge path for SharePoint Online, OneDrive for Business, and Teams files, complete these steps:</span></span>

1. <span data-ttu-id="bf6a4-210">Отзыв доступа к Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-210">Revoke Azure Key Vault access.</span></span> <span data-ttu-id="bf6a4-211">Все администраторы основного хранилища должны согласиться на отзыв доступа.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-211">All key vault admins must agree to revoke access.</span></span>

   <span data-ttu-id="bf6a4-212">Вы не удаляете Azure Key Vault для SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-212">You do not delete the Azure Key Vault for SharePoint Online.</span></span> <span data-ttu-id="bf6a4-213">Основные хранилища могут быть общими для нескольких клиентов SharePoint Online и ДЕПС.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-213">Key vaults may be shared among several SharePoint Online tenants and DEPs.</span></span>

2. <span data-ttu-id="bf6a4-214">Обратитесь в корпорацию Майкрософт, чтобы удалить ключ доступности.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-214">Contact Microsoft to delete the availability key.</span></span>

    <span data-ttu-id="bf6a4-215">Когда вы обратитесь в корпорацию Майкрософт, чтобы удалить ключ доступности, мы отправим вам юридический документ.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-215">When you contact Microsoft to delete the availability key, we'll send you a legal document.</span></span> <span data-ttu-id="bf6a4-216">Этот документ должен быть подписан сотрудником вашей организации, который зарегистрировался в качестве утверждающего в FastTrack.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-216">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="bf6a4-217">Как правило, это руководитель или другой сотрудник компании, уполномоченный подписывать документы от имени вашей организации.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-217">Normally, this is an executive or other designated person in your company who's legally authorized to sign the paperwork on behalf of your organization.</span></span>

3. <span data-ttu-id="bf6a4-218">Когда ваш представитель подписывает юридический документ, верните его в корпорацию Майкрософт (обычно через подпись едок).</span><span class="sxs-lookup"><span data-stu-id="bf6a4-218">Once your representative signs the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

   <span data-ttu-id="bf6a4-219">Когда корпорация Майкрософт получает юридический документ, мы выполняем командлеты для запуска очистки данных, которая выполняет удаление шифрования ключа клиента, ключа сайта и всех отдельных ключей документа, ирревокабли нарушая иерархию ключей.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-219">Once Microsoft receives the legal document, we run cmdlets to trigger the data purge which performs crypto deletion of the tenant key, site key, and all individual per-document keys, irrevocably breaking the key hierarchy.</span></span> <span data-ttu-id="bf6a4-220">После завершения командлетов по очистке данных данные очищаются.</span><span class="sxs-lookup"><span data-stu-id="bf6a4-220">Once the data purge cmdlets complete, your data has been purged.</span></span>

## <a name="related-articles"></a><span data-ttu-id="bf6a4-221">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="bf6a4-221">Related articles</span></span>

- [<span data-ttu-id="bf6a4-222">Шифрование службы с помощью ключа клиента</span><span class="sxs-lookup"><span data-stu-id="bf6a4-222">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="bf6a4-223">Сведения о ключе доступности</span><span class="sxs-lookup"><span data-stu-id="bf6a4-223">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="bf6a4-224">Настройка ключа клиента</span><span class="sxs-lookup"><span data-stu-id="bf6a4-224">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="bf6a4-225">Смена или ротация ключа клиента или ключа доступности</span><span class="sxs-lookup"><span data-stu-id="bf6a4-225">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="bf6a4-226">Защищенное хранилище пользователя</span><span class="sxs-lookup"><span data-stu-id="bf6a4-226">Customer Lockbox</span></span>](customer-lockbox-requests.md)

- [<span data-ttu-id="bf6a4-227">Шифрование службы</span><span class="sxs-lookup"><span data-stu-id="bf6a4-227">Service Encryption</span></span>](office-365-service-encryption.md)
