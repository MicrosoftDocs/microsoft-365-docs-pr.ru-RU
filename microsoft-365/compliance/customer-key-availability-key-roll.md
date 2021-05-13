---
title: Смена или ротация ключа клиента или ключа доступности
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Узнайте, как свернуть корневые ключи клиента, хранимые в Хранилище ключей Azure, которые используются с ключом клиента. Службы включают Exchange Online, Skype для бизнеса, SharePoint Online, OneDrive для бизнеса и Teams файлы.
ms.openlocfilehash: 892d77959bec1fb33b0ea6bcfaa8c530dd9b8911
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345122"
---
# <a name="roll-or-rotate-a-customer-key-or-an-availability-key"></a><span data-ttu-id="2effc-104">Смена или ротация ключа клиента или ключа доступности</span><span class="sxs-lookup"><span data-stu-id="2effc-104">Roll or rotate a Customer Key or an availability key</span></span>

> [!CAUTION]
> <span data-ttu-id="2effc-105">Только свернуть ключ шифрования, который используется с ключом клиента, когда требования безопасности или соответствия требованиям диктуют, что вы должны свернуть ключ.</span><span class="sxs-lookup"><span data-stu-id="2effc-105">Only roll an encryption key that you use with Customer Key when your security or compliance requirements dictate that you must roll the key.</span></span> <span data-ttu-id="2effc-106">Кроме того, не удаляйте ключи, связанные или связанные с политиками.</span><span class="sxs-lookup"><span data-stu-id="2effc-106">In addition, do not delete any keys that are or were associated with policies.</span></span> <span data-ttu-id="2effc-107">При откате ключей будет зашифровано содержимое с предыдущими ключами.</span><span class="sxs-lookup"><span data-stu-id="2effc-107">When you roll your keys, there will be content encrypted with the previous keys.</span></span> <span data-ttu-id="2effc-108">Например, в то время как активные почтовые ящики будут часто повторно шифроваться, неактивные, отключенные и отключенные почтовые ящики могут по-прежнему шифроваться с предыдущими ключами.</span><span class="sxs-lookup"><span data-stu-id="2effc-108">For example, while active mailboxes will be re-encrypted frequently, inactive, disconnected, and disabled mailboxes may still be encrypted with the previous keys.</span></span> <span data-ttu-id="2effc-109">SharePoint В Интернете выполняется резервное копирование контента для восстановления и восстановления, поэтому может по-прежнему архивироваться содержимое с помощью старых ключей.</span><span class="sxs-lookup"><span data-stu-id="2effc-109">SharePoint Online performs backup of content for restore and recovery purposes, so there may still be archived content using older keys.</span></span>

## <a name="about-rolling-the-availability-key"></a><span data-ttu-id="2effc-110">О перекатке ключа доступности</span><span class="sxs-lookup"><span data-stu-id="2effc-110">About rolling the availability key</span></span>

<span data-ttu-id="2effc-111">Корпорация Майкрософт не предоставляет пользователям прямой контроль ключа доступности.</span><span class="sxs-lookup"><span data-stu-id="2effc-111">Microsoft does not expose direct control of the availability key to customers.</span></span> <span data-ttu-id="2effc-112">Например, вы можете свернуть (повернуть) только ключи, которые принадлежат вам в Хранилище ключей Azure.</span><span class="sxs-lookup"><span data-stu-id="2effc-112">For example, you can only roll (rotate) the keys that you own in Azure Key Vault.</span></span> <span data-ttu-id="2effc-113">Microsoft 365 перекатываю клавиши доступности по внутренне определенному расписанию.</span><span class="sxs-lookup"><span data-stu-id="2effc-113">Microsoft 365 rolls the availability keys on an internally-defined schedule.</span></span> <span data-ttu-id="2effc-114">Для этих рулонов ключей не существует соглашения на уровне обслуживания с клиентом.</span><span class="sxs-lookup"><span data-stu-id="2effc-114">There is no customer-facing, service-level agreement (SLA) for these key rolls.</span></span> <span data-ttu-id="2effc-115">Microsoft 365 поворот ключа доступности с Microsoft 365 кодом службы в автоматизированном, не ручном процессе.</span><span class="sxs-lookup"><span data-stu-id="2effc-115">Microsoft 365 rotates the availability key using Microsoft 365 service code in an automated, non-manual process.</span></span> <span data-ttu-id="2effc-116">Администраторы Майкрософт могут инициировать процесс ролла.</span><span class="sxs-lookup"><span data-stu-id="2effc-116">Microsoft administrators may initiate the roll process.</span></span> <span data-ttu-id="2effc-117">Ключ свернут с помощью автоматизированных механизмов без прямого доступа к хранилище ключей.</span><span class="sxs-lookup"><span data-stu-id="2effc-117">The key is rolled using automated mechanisms without direct access to the key store.</span></span> <span data-ttu-id="2effc-118">Доступ к хранилище секретного ключа доступности не предусмотрен администраторам Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="2effc-118">Access to the availability key secret store is not provisioned to Microsoft administrators.</span></span> <span data-ttu-id="2effc-119">Прокатка ключа доступности использует тот же механизм, который использовался для первоначального создания ключа.</span><span class="sxs-lookup"><span data-stu-id="2effc-119">Availability key rolling leverages the same mechanism used to initially generate the key.</span></span> <span data-ttu-id="2effc-120">Дополнительные сведения о ключе доступности см. в дополнительных сведениях [о ключе доступности.](customer-key-availability-key-understand.md)</span><span class="sxs-lookup"><span data-stu-id="2effc-120">For more information about the availability key, see [Understand the availability key](customer-key-availability-key-understand.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2effc-121">Exchange Online и Skype для бизнеса могут эффективно свернуться клиентами, создавав новый deP, так как для каждого создаваемого deP создается уникальный ключ доступности.</span><span class="sxs-lookup"><span data-stu-id="2effc-121">Exchange Online and Skype for Business availability keys can be effectively rolled by customers creating a new DEP, since a unique availability key is generated for each DEP you create.</span></span> <span data-ttu-id="2effc-122">Ключи доступности для SharePoint, OneDrive для бизнеса и Teams файлов существуют на уровне леса и делятся между dePs и клиентами, что означает, что развертывание происходит только в определенном microsoft расписания.</span><span class="sxs-lookup"><span data-stu-id="2effc-122">Availability keys for SharePoint Online, OneDrive for Business, and Teams files exist at the forest level and are shared across DEPs and customers, which means rolling only occurs at a Microsoft internally defined schedule.</span></span> <span data-ttu-id="2effc-123">Чтобы уменьшить риск не перекатывания ключа доступности каждый раз, когда создается новый deP, SharePoint, OneDrive и Teams перекатывать промежуточный ключ клиента (TIK), ключ, завернутый корневыми ключами клиента и ключом доступности, каждый раз, когда создается новый deP.</span><span class="sxs-lookup"><span data-stu-id="2effc-123">To mitigate the risk of not rolling the availability key each time a new DEP is created, SharePoint, OneDrive, and Teams roll the tenant intermediate key (TIK), the key wrapped by the customer root keys and availability key, each time a new DEP is created.</span></span>

## <a name="request-a-new-version-of-each-existing-root-key-you-want-to-roll"></a><span data-ttu-id="2effc-124">Запрос новой версии каждого существующего корневого ключа, который необходимо свернуть</span><span class="sxs-lookup"><span data-stu-id="2effc-124">Request a new version of each existing root key you want to roll</span></span>

<span data-ttu-id="2effc-125">При скатыве ключа необходимо запросить новую версию существующего ключа.</span><span class="sxs-lookup"><span data-stu-id="2effc-125">When you roll a key, you request a new version of an existing key.</span></span> <span data-ttu-id="2effc-126">Чтобы запросить новую версию существующего ключа, вы используете тот же кодлет [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey)с тем же синтаксисом, что и для создания ключа.</span><span class="sxs-lookup"><span data-stu-id="2effc-126">To request a new version of an existing key, you use the same cmdlet, [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey), with the same syntax that you used to create the key in the first place.</span></span> <span data-ttu-id="2effc-127">После завершения проката любого ключа, связанного с политикой шифрования данных (DEP), вы запустите еще один комдлет, чтобы клиентский ключ начал использовать новый ключ.</span><span class="sxs-lookup"><span data-stu-id="2effc-127">After you've finished rolling any key associated with a Data Encryption Policy (DEP), you run another cmdlet to ensure that Customer Key begins using the new key.</span></span> <span data-ttu-id="2effc-128">Сделайте этот шаг в каждом хранилище ключей Azure (AKV).</span><span class="sxs-lookup"><span data-stu-id="2effc-128">Do this step in each Azure Key Vault (AKV).</span></span>

<span data-ttu-id="2effc-129">Например:</span><span class="sxs-lookup"><span data-stu-id="2effc-129">For example:</span></span>

1. <span data-ttu-id="2effc-130">Вопишите свою подписку Azure с помощью Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2effc-130">Sign in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="2effc-131">Инструкции см. в [Azure PowerShell.](/powershell/azure/authenticate-azureps)</span><span class="sxs-lookup"><span data-stu-id="2effc-131">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="2effc-132">Запустите Add-AzKeyVaultKey, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="2effc-132">Run the Add-AzKeyVaultKey cmdlet as shown in the following example:</span></span>

   ```powershell
   Add-AzKeyVaultKey -VaultName Contoso-CK-EX-NA-VaultA1 -Name Contoso-CK-EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
   ```

   <span data-ttu-id="2effc-133">В этом примере, так как ключ **Contoso-CK-EX-NA-VaultA1-Key001** существует в хранилище **Contoso-CK-EX-NA-VaultA1,** в этом ключе создается новая версия ключа.</span><span class="sxs-lookup"><span data-stu-id="2effc-133">In this example, since a key named **Contoso-CK-EX-NA-VaultA1-Key001** exists in the **Contoso-CK-EX-NA-VaultA1** vault, the cmdlet creates a new version of the key.</span></span> <span data-ttu-id="2effc-134">Эта операция сохраняет предыдущие ключевые версии в истории версий для ключа.</span><span class="sxs-lookup"><span data-stu-id="2effc-134">This operation preserves the previous key versions in the version history for the key.</span></span> <span data-ttu-id="2effc-135">Для расшифровки данных, которые она по-прежнему шифрует, нужна предыдущая версия ключа.</span><span class="sxs-lookup"><span data-stu-id="2effc-135">You need the previous key version to decrypt the data that it still encrypts.</span></span> <span data-ttu-id="2effc-136">После завершения проката любого ключа, связанного с deP, запустите дополнительный кодлет, чтобы убедиться, что ключ клиента начинает использовать новый ключ.</span><span class="sxs-lookup"><span data-stu-id="2effc-136">Once you complete rolling any key associated with a DEP,  run an extra cmdlet to ensure that Customer Key begins using the new key.</span></span> <span data-ttu-id="2effc-137">В следующих разделах описаны более подробные разделы.</span><span class="sxs-lookup"><span data-stu-id="2effc-137">The following sections describe the cmdlets in more detail.</span></span>
  
## <a name="update-the-keys-for-multi-workload-deps"></a><span data-ttu-id="2effc-138">Обновление ключей для многопрофильных dePs</span><span class="sxs-lookup"><span data-stu-id="2effc-138">Update the keys for multi-workload DEPs</span></span>

<span data-ttu-id="2effc-139">Когда вы свернуть любой из ключей Хранилища Azure, связанных с deP, используемым с несколькими рабочими нагрузками, необходимо обновить DEP, чтобы указать на новый ключ.</span><span class="sxs-lookup"><span data-stu-id="2effc-139">When you roll either of the Azure Key Vault keys associated with a DEP used with multiple workloads, you must update the DEP to point to the new key.</span></span> <span data-ttu-id="2effc-140">Этот процесс не вращает ключ доступности.</span><span class="sxs-lookup"><span data-stu-id="2effc-140">This process does not rotate the availability key.</span></span>

<span data-ttu-id="2effc-141">Чтобы поручить ключу клиента использовать новый ключ для шифрования нескольких рабочих нагрузок, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="2effc-141">To instruct Customer Key to use the new key to encrypt multiple workloads, complete these steps:</span></span>

1. <span data-ttu-id="2effc-142">На локальном компьютере с помощью учетной записи работы или учебного заведения с разрешениями администратора глобального администратора или администратора соответствия требованиям подключайтесь к Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) в Windows PowerShell окне.</span><span class="sxs-lookup"><span data-stu-id="2effc-142">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="2effc-143">Запустите Set-M365DataAtRestEncryptionPolicy.</span><span class="sxs-lookup"><span data-stu-id="2effc-143">Run the Set-M365DataAtRestEncryptionPolicy cmdlet.</span></span>
  
   ```powershell
   Set-M365DataAtRestEncryptionPolicy -[Identity] "PolicyName" -Refresh
   ```

<span data-ttu-id="2effc-144">Где *PolicyName* — это имя или уникальный ID политики.</span><span class="sxs-lookup"><span data-stu-id="2effc-144">Where *PolicyName* is the name or unique ID of the policy.</span></span> <span data-ttu-id="2effc-145">Например, Contoso_Global.</span><span class="sxs-lookup"><span data-stu-id="2effc-145">For example, Contoso_Global.</span></span>

<span data-ttu-id="2effc-146">Пример:</span><span class="sxs-lookup"><span data-stu-id="2effc-146">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global" -Refresh
```

## <a name="update-the-keys-for-exchange-online-deps"></a><span data-ttu-id="2effc-147">Обновление ключей для Exchange Online dePs</span><span class="sxs-lookup"><span data-stu-id="2effc-147">Update the keys for Exchange Online DEPs</span></span>

<span data-ttu-id="2effc-148">Когда вы свернуть один из ключей Хранилища Azure, связанных с deP, используемым с Exchange Online и Skype для бизнеса, необходимо обновить deP, чтобы указать на новый ключ.</span><span class="sxs-lookup"><span data-stu-id="2effc-148">When you roll either of the Azure Key Vault keys associated with a DEP used with Exchange Online and Skype for Business, you must update the DEP to point to the new key.</span></span> <span data-ttu-id="2effc-149">Это не вращает ключ доступности.</span><span class="sxs-lookup"><span data-stu-id="2effc-149">This does not rotate the availability key.</span></span>

<span data-ttu-id="2effc-150">Чтобы поручить ключу клиента использовать новый ключ для шифрования почтовых ящиков, выполните Set-DataEncryptionPolicy кодлета следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2effc-150">To instruct Customer Key to use the new key to encrypt mailboxes, run the Set-DataEncryptionPolicy cmdlet as follows:</span></span>

1. <span data-ttu-id="2effc-151">Запустите Set-DataEncryptionPolicy в Azure PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2effc-151">Run the Set-DataEncryptionPolicy cmdlet in Azure PowerShell:</span></span>
  
   ```powershell
   Set-DataEncryptionPolicy -Identity <DataEncryptionPolicyID> -Refresh
   ```

2. <span data-ttu-id="2effc-152">Чтобы проверить значение свойства DataEncryptionPolicyID для почтового ящика, используйте шаги в Определении deP, назначенного [почтовому ящику.](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox)</span><span class="sxs-lookup"><span data-stu-id="2effc-152">To check the value for the DataEncryptionPolicyID property for the mailbox, use the steps in [Determine the DEP assigned to a mailbox](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox).</span></span> <span data-ttu-id="2effc-153">Значение этого свойства изменяется после того, как служба применяет обновленный ключ.</span><span class="sxs-lookup"><span data-stu-id="2effc-153">The value for this property changes once the service applies the updated key.</span></span>
  
## <a name="update-the-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="2effc-154">Обновление ключей для SharePoint, OneDrive для бизнеса и Teams файлов</span><span class="sxs-lookup"><span data-stu-id="2effc-154">Update the keys for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="2effc-155">SharePoint Он-лайн позволяет одновременно свернуть только один ключ.</span><span class="sxs-lookup"><span data-stu-id="2effc-155">SharePoint Online only allows you to roll one key at a time.</span></span> <span data-ttu-id="2effc-156">Если вы хотите свернуть оба ключа в хранилище ключей, дождись завершения первой операции.</span><span class="sxs-lookup"><span data-stu-id="2effc-156">If you want to roll both keys in a key vault, wait for the first operation to complete.</span></span> <span data-ttu-id="2effc-157">Корпорация Майкрософт рекомендует шатания операций, чтобы избежать этой проблемы.</span><span class="sxs-lookup"><span data-stu-id="2effc-157">Microsoft recommends that you stagger your operations to avoid this issue.</span></span> <span data-ttu-id="2effc-158">Когда вы свернуть один из ключей Хранилища Azure, связанных с deP, используемым с SharePoint Online и OneDrive для бизнеса, необходимо обновить deP, чтобы указать на новый ключ.</span><span class="sxs-lookup"><span data-stu-id="2effc-158">When you roll either of the Azure Key Vault keys associated with a DEP used with SharePoint Online and OneDrive for Business, you must update the DEP to point to the new key.</span></span> <span data-ttu-id="2effc-159">Это не вращает ключ доступности.</span><span class="sxs-lookup"><span data-stu-id="2effc-159">This does not rotate the availability key.</span></span>

1. <span data-ttu-id="2effc-160">Выполните Update-SPODataEncryptionPolicy следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2effc-160">Run the Update-SPODataEncryptionPolicy cmdlet as follows:</span></span>
  
   ```powershell
   Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
   ```

   <span data-ttu-id="2effc-161">Несмотря на то, что этот комдлет запускает операцию переката ключей для SharePoint Online и OneDrive для бизнеса, действие не завершается сразу.</span><span class="sxs-lookup"><span data-stu-id="2effc-161">While this cmdlet starts the key roll operation for SharePoint Online and OneDrive for Business, the action doesn't complete immediately.</span></span>

2. <span data-ttu-id="2effc-162">Чтобы увидеть ход операции рулона ключей, выполните Get-SPODataEncryptionPolicy следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2effc-162">To see the progress of the key roll operation, run the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

   ```powershell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
   ```

## <a name="related-articles"></a><span data-ttu-id="2effc-163">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="2effc-163">Related articles</span></span>

- [<span data-ttu-id="2effc-164">Шифрование службы с ключом клиента для Office 365</span><span class="sxs-lookup"><span data-stu-id="2effc-164">Service encryption with Customer Key for Office 365</span></span>](customer-key-overview.md)

- [<span data-ttu-id="2effc-165">Настройка ключа клиента для Office 365</span><span class="sxs-lookup"><span data-stu-id="2effc-165">Set up Customer Key for Office 365</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="2effc-166">Управление ключом клиента для Office 365</span><span class="sxs-lookup"><span data-stu-id="2effc-166">Manage Customer Key for Office 365</span></span>](customer-key-manage.md)

- [<span data-ttu-id="2effc-167">Узнайте о ключе доступности</span><span class="sxs-lookup"><span data-stu-id="2effc-167">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)