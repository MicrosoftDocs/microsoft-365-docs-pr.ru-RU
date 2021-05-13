---
title: Управление ключом клиента
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
description: После создания ключа клиента узнайте, как управлять им, восстановив ключи AKV, а также управляя разрешениями и создав и назначив политики шифрования данных.
ms.openlocfilehash: da806ec9dcf1327ec5fdd6b0a0c9e7f22c89584e
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345062"
---
# <a name="manage-customer-key"></a><span data-ttu-id="3d85c-103">Управление ключом клиента</span><span class="sxs-lookup"><span data-stu-id="3d85c-103">Manage Customer Key</span></span>

<span data-ttu-id="3d85c-104">После создания ключа клиента для Office 365 необходимо создать и назначить одну или несколько политик шифрования данных (DEP).</span><span class="sxs-lookup"><span data-stu-id="3d85c-104">After you've set up Customer Key for Office 365, you'll need to create and assign one or more data encryption policies (DEP).</span></span> <span data-ttu-id="3d85c-105">После того как вы направите dePs, вы сможете управлять ключами, как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="3d85c-105">Once you've assigned your DEPs, you can manage your keys as described in this article.</span></span> <span data-ttu-id="3d85c-106">Дополнительные данные о ключе клиента в связанных темах.</span><span class="sxs-lookup"><span data-stu-id="3d85c-106">Learn more about Customer Key in the related topics.</span></span>

## <a name="create-a-dep-for-use-with-multiple-workloads-for-all-tenant-users"></a><span data-ttu-id="3d85c-107">Создание deP для использования с несколькими рабочими нагрузками для всех пользователей-клиентов</span><span class="sxs-lookup"><span data-stu-id="3d85c-107">Create a DEP for use with multiple workloads for all tenant users</span></span>

<span data-ttu-id="3d85c-108">Перед началом работы убедитесь, что вы выполнили задачи, необходимые для набора клиента.</span><span class="sxs-lookup"><span data-stu-id="3d85c-108">Before you begin, ensure that you've completed the tasks required to set up Customer.</span></span> <span data-ttu-id="3d85c-109">Сведения см. в [перенастройка клиентского ключа](customer-key-set-up.md).</span><span class="sxs-lookup"><span data-stu-id="3d85c-109">For information, see [Set up Customer Key](customer-key-set-up.md).</span></span> <span data-ttu-id="3d85c-110">Чтобы создать DEP, вам нужны URL-адреса key Vault, полученные во время установки.</span><span class="sxs-lookup"><span data-stu-id="3d85c-110">To create the DEP, you need the Key Vault URIs you obtained during setup.</span></span> <span data-ttu-id="3d85c-111">Сведения см. в [элементе Получение URI для каждого ключа Azure Key Vault.](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)</span><span class="sxs-lookup"><span data-stu-id="3d85c-111">For information, see [Obtain the URI for each Azure Key Vault key](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span></span>

<span data-ttu-id="3d85c-112">Чтобы создать deP с несколькими рабочими нагрузками, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="3d85c-112">To create a multi-workload DEP, follow these steps:</span></span>
  
1. <span data-ttu-id="3d85c-113">На локальном компьютере с помощью учетной записи работы или учебного заведения с разрешениями администратора глобального администратора или администратора соответствия требованиям подключайтесь к Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) в Windows PowerShell окне.</span><span class="sxs-lookup"><span data-stu-id="3d85c-113">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="3d85c-114">Чтобы создать DEP, используйте New-M365DataAtRestEncryptionPolicy.</span><span class="sxs-lookup"><span data-stu-id="3d85c-114">To create a DEP, use the New-M365DataAtRestEncryptionPolicy cmdlet.</span></span>

   ```powershell
   New-M365DataAtRestEncryptionPolicy -Name <PolicyName> -AzureKeyIDs <KeyVaultURI1, KeyVaultURI2> [-Description <String>]
   ```

   <span data-ttu-id="3d85c-115">Где:</span><span class="sxs-lookup"><span data-stu-id="3d85c-115">Where:</span></span>

   - <span data-ttu-id="3d85c-116">*PolicyName* — это имя, которое необходимо использовать для политики.</span><span class="sxs-lookup"><span data-stu-id="3d85c-116">*PolicyName* is the name you want to use for the policy.</span></span> <span data-ttu-id="3d85c-117">Имена не могут содержать пробелы.</span><span class="sxs-lookup"><span data-stu-id="3d85c-117">Names can't contain spaces.</span></span> <span data-ttu-id="3d85c-118">Например, Contoso_Global.</span><span class="sxs-lookup"><span data-stu-id="3d85c-118">For example, Contoso_Global.</span></span>

   - <span data-ttu-id="3d85c-119">*KeyVaultURI1* — это URI для первого ключа в политике.</span><span class="sxs-lookup"><span data-stu-id="3d85c-119">*KeyVaultURI1* is the URI for the first key in the policy.</span></span> <span data-ttu-id="3d85c-120">Например, <https://contosoWestUSvault1.vault.azure.net/keys/Key_01>.</span><span class="sxs-lookup"><span data-stu-id="3d85c-120">For example, <https://contosoWestUSvault1.vault.azure.net/keys/Key_01>.</span></span>

   - <span data-ttu-id="3d85c-121">*KeyVaultURI2* — это URI для второго ключа в политике.</span><span class="sxs-lookup"><span data-stu-id="3d85c-121">*KeyVaultURI2* is the URI for the second key in the policy.</span></span> <span data-ttu-id="3d85c-122">Например, <https://contosoCentralUSvault1.vault.azure.net/keys/Key_02>.</span><span class="sxs-lookup"><span data-stu-id="3d85c-122">For example, <https://contosoCentralUSvault1.vault.azure.net/keys/Key_02>.</span></span> <span data-ttu-id="3d85c-123">Разделять два URL-адреса на запятую и пробел.</span><span class="sxs-lookup"><span data-stu-id="3d85c-123">Separate the two URIs by a comma and a space.</span></span>

   - <span data-ttu-id="3d85c-124">*Описание политики* — это удобное описание политики, которое поможет вам вспомнить, для чего нужна политика.</span><span class="sxs-lookup"><span data-stu-id="3d85c-124">*Policy Description* is a user-friendly description of the policy that will help you remember what the policy is for.</span></span> <span data-ttu-id="3d85c-125">В описании можно включить пробелы.</span><span class="sxs-lookup"><span data-stu-id="3d85c-125">You can include spaces in the description.</span></span> <span data-ttu-id="3d85c-126">Например, "Корневая политика для нескольких рабочих нагрузок для всех пользователей в клиенте".</span><span class="sxs-lookup"><span data-stu-id="3d85c-126">For example, "Root policy for multiple workloads for all users in the tenant.".</span></span>

<span data-ttu-id="3d85c-127">Пример:</span><span class="sxs-lookup"><span data-stu-id="3d85c-127">Example:</span></span>

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Contoso_Global" -AzureKeyIDs "https://contosoWestUSvault1.vault.azure.net/keys/Key_01","https://contosoCentralUSvault1.vault.azure.net/keys/Key_02" -Description "Policy for multiple workloads for all users in the tenant."
```

### <a name="assign-multi-workload-policy"></a><span data-ttu-id="3d85c-128">Назначение политики с несколькими рабочими нагрузками</span><span class="sxs-lookup"><span data-stu-id="3d85c-128">Assign multi-workload policy</span></span>

<span data-ttu-id="3d85c-129">Назначение deP с помощью Set-M365DataAtRestEncryptionPolicyAssignment.</span><span class="sxs-lookup"><span data-stu-id="3d85c-129">Assign the DEP by using the Set-M365DataAtRestEncryptionPolicyAssignment cmdlet.</span></span> <span data-ttu-id="3d85c-130">После назначения политики Microsoft 365 шифровать данные с помощью ключа, идентифицированного в deP.</span><span class="sxs-lookup"><span data-stu-id="3d85c-130">Once you assign the policy, Microsoft 365 encrypts the data with the key identified in the DEP.</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy <PolicyName or ID>
```

 <span data-ttu-id="3d85c-131">Где *PolicyName* — это имя политики.</span><span class="sxs-lookup"><span data-stu-id="3d85c-131">Where *PolicyName* is the name of the policy.</span></span> <span data-ttu-id="3d85c-132">Например, Contoso_Global.</span><span class="sxs-lookup"><span data-stu-id="3d85c-132">For example, Contoso_Global.</span></span>

<span data-ttu-id="3d85c-133">Пример:</span><span class="sxs-lookup"><span data-stu-id="3d85c-133">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "Contoso_Global"
```

## <a name="create-a-dep-for-use-with-exchange-online-mailboxes"></a><span data-ttu-id="3d85c-134">Создание deP для использования с Exchange Online почтовыми ящиками</span><span class="sxs-lookup"><span data-stu-id="3d85c-134">Create a DEP for use with Exchange Online mailboxes</span></span>

<span data-ttu-id="3d85c-135">Перед началом работы убедитесь, что вы выполнили задачи, необходимые для набора хранилища ключей Azure.</span><span class="sxs-lookup"><span data-stu-id="3d85c-135">Before you begin, ensure that you've completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="3d85c-136">Сведения см. в [перенастройка клиентского ключа](customer-key-set-up.md).</span><span class="sxs-lookup"><span data-stu-id="3d85c-136">For information, see [Set up Customer Key](customer-key-set-up.md).</span></span> <span data-ttu-id="3d85c-137">Вы выполните эти действия, удаленно подключившись к Exchange Online с Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3d85c-137">You'll complete these steps by remotely connecting to Exchange Online with Windows PowerShell.</span></span>

<span data-ttu-id="3d85c-138">DeP связан с набором ключей, хранимых в хранилище ключей Azure.</span><span class="sxs-lookup"><span data-stu-id="3d85c-138">A DEP is associated with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="3d85c-139">Вы назначаете deP почтовому ящику в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3d85c-139">You assign a DEP to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="3d85c-140">Microsoft 365 затем использовать ключи, выявленные в политике, для шифрования почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="3d85c-140">Microsoft 365 will then use the keys identified in the policy to encrypt the mailbox.</span></span> <span data-ttu-id="3d85c-141">Чтобы создать DEP, вам нужны URL-адреса key Vault, полученные во время установки.</span><span class="sxs-lookup"><span data-stu-id="3d85c-141">To create the DEP, you need the Key Vault URIs you obtained during setup.</span></span> <span data-ttu-id="3d85c-142">Сведения см. в [элементе Получение URI для каждого ключа Azure Key Vault.](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)</span><span class="sxs-lookup"><span data-stu-id="3d85c-142">For information, see [Obtain the URI for each Azure Key Vault key](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span></span>

<span data-ttu-id="3d85c-143">Помните!</span><span class="sxs-lookup"><span data-stu-id="3d85c-143">Remember!</span></span> <span data-ttu-id="3d85c-144">При создании DEP укажите два ключа в двух разных хранилищах ключей Azure.</span><span class="sxs-lookup"><span data-stu-id="3d85c-144">When you create a DEP, you specify two keys in two different Azure Key Vaults.</span></span> <span data-ttu-id="3d85c-145">Создайте эти клавиши в двух отдельных регионах Azure для обеспечения избыточности геоизбытки.</span><span class="sxs-lookup"><span data-stu-id="3d85c-145">Create these keys in two separate Azure regions to ensure geo-redundancy.</span></span>

<span data-ttu-id="3d85c-146">Чтобы создать deP для использования с почтовым ящиком, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="3d85c-146">To create a DEP to use with a mailbox, follow these steps:</span></span>
  
1. <span data-ttu-id="3d85c-147">На локальном компьютере с помощью учетной записи работы или учебного заведения с разрешениями глобального администратора или администратора Exchange Online администратора в организации подключите Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) в окне Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3d85c-147">On your local computer, using a work or school account that has global administrator or Exchange Online admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="3d85c-148">Чтобы создать deP, используйте командлет New-DataEncryptionPolicy, введя следующую команду.</span><span class="sxs-lookup"><span data-stu-id="3d85c-148">To create a DEP, use the New-DataEncryptionPolicy cmdlet by typing the following command.</span></span>

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   <span data-ttu-id="3d85c-149">Где:</span><span class="sxs-lookup"><span data-stu-id="3d85c-149">Where:</span></span>

   - <span data-ttu-id="3d85c-150">*PolicyName* — это имя, которое необходимо использовать для политики.</span><span class="sxs-lookup"><span data-stu-id="3d85c-150">*PolicyName* is the name you want to use for the policy.</span></span> <span data-ttu-id="3d85c-151">Имена не могут содержать пробелы.</span><span class="sxs-lookup"><span data-stu-id="3d85c-151">Names can't contain spaces.</span></span> <span data-ttu-id="3d85c-152">Например, USA_mailboxes.</span><span class="sxs-lookup"><span data-stu-id="3d85c-152">For example, USA_mailboxes.</span></span>

   - <span data-ttu-id="3d85c-153">*Описание политики* — это удобное описание политики, которое поможет вам вспомнить, для чего нужна политика.</span><span class="sxs-lookup"><span data-stu-id="3d85c-153">*Policy Description* is a user-friendly description of the policy that will help you remember what the policy is for.</span></span> <span data-ttu-id="3d85c-154">В описании можно включить пробелы.</span><span class="sxs-lookup"><span data-stu-id="3d85c-154">You can include spaces in the description.</span></span> <span data-ttu-id="3d85c-155">Например, "Корневой ключ для почтовых ящиков в США и на ее территориях".</span><span class="sxs-lookup"><span data-stu-id="3d85c-155">For example, "Root key for mailboxes in USA and its territories".</span></span>

   - <span data-ttu-id="3d85c-156">*KeyVaultURI1* — это URI для первого ключа в политике.</span><span class="sxs-lookup"><span data-stu-id="3d85c-156">*KeyVaultURI1* is the URI for the first key in the policy.</span></span> <span data-ttu-id="3d85c-157">Например, <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>.</span><span class="sxs-lookup"><span data-stu-id="3d85c-157">For example, <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>.</span></span>

   - <span data-ttu-id="3d85c-158">*KeyVaultURI2* — это URI для второго ключа в политике.</span><span class="sxs-lookup"><span data-stu-id="3d85c-158">*KeyVaultURI2* is the URI for the second key in the policy.</span></span> <span data-ttu-id="3d85c-159">Например, <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>.</span><span class="sxs-lookup"><span data-stu-id="3d85c-159">For example, <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>.</span></span> <span data-ttu-id="3d85c-160">Разделять два URL-адреса на запятую и пробел.</span><span class="sxs-lookup"><span data-stu-id="3d85c-160">Separate the two URIs by a comma and a space.</span></span>

   <span data-ttu-id="3d85c-161">Пример:</span><span class="sxs-lookup"><span data-stu-id="3d85c-161">Example:</span></span>
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault02.vault.azure.net/keys/USA_key_01, https://contoso_CentralUSvault02.vault.azure.net/keys/USA_Key_02
   ```

<span data-ttu-id="3d85c-162">Подробные сведения о синтаксисах и параметрах см. [в обзоре New-DataEncryptionPolicy.](/powershell/module/exchange/new-data-encryptionpolicy)</span><span class="sxs-lookup"><span data-stu-id="3d85c-162">For detailed syntax and parameter information, see [New-DataEncryptionPolicy](/powershell/module/exchange/new-data-encryptionpolicy).</span></span>

### <a name="assign-a-dep-to-a-mailbox"></a><span data-ttu-id="3d85c-163">Назначение deP почтовому ящику</span><span class="sxs-lookup"><span data-stu-id="3d85c-163">Assign a DEP to a mailbox</span></span>

<span data-ttu-id="3d85c-164">Назначение deP почтовому ящику с помощью Set-Mailbox.</span><span class="sxs-lookup"><span data-stu-id="3d85c-164">Assign the DEP to a mailbox by using the Set-Mailbox cmdlet.</span></span> <span data-ttu-id="3d85c-165">После назначения политики Microsoft 365 шифровать почтовый ящик ключом, идентифицированным в deP.</span><span class="sxs-lookup"><span data-stu-id="3d85c-165">Once you assign the policy, Microsoft 365 can encrypt the mailbox with the key identified in the DEP.</span></span>
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="3d85c-166">Где *MailboxIdParameter* указывает почтовый ящик пользователя.</span><span class="sxs-lookup"><span data-stu-id="3d85c-166">Where *MailboxIdParameter* specifies a user mailbox.</span></span> <span data-ttu-id="3d85c-167">Дополнительные сведения о Set-Mailbox см. в [списке Set-Mailbox.](/powershell/module/exchange/set-mailbox)</span><span class="sxs-lookup"><span data-stu-id="3d85c-167">For more information about the Set-Mailbox cmdlet, see [Set-Mailbox](/powershell/module/exchange/set-mailbox).</span></span>

<span data-ttu-id="3d85c-168">В гибридных средах можно назначить deP данным локального почтового ящика, синхронизированным в Exchange Online клиента.</span><span class="sxs-lookup"><span data-stu-id="3d85c-168">In hybrid environments, you can assign a DEP to the on-premises mailbox data that is synchronized into your Exchange Online tenant.</span></span> <span data-ttu-id="3d85c-169">Чтобы назначить deP этим синхронизированным данным почтовых ящиков, вы будете использовать Set-MailUser.</span><span class="sxs-lookup"><span data-stu-id="3d85c-169">To assign a DEP to this synchronized mailbox data, you'll use the Set-MailUser cmdlet.</span></span> <span data-ttu-id="3d85c-170">Дополнительные сведения о данных почтовых ящиков в гибридной среде см. в локальном почтовом ящике с Outlook для iOS и Android с гибридной современной проверкой [подлинности.](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)</span><span class="sxs-lookup"><span data-stu-id="3d85c-170">For more information about mailbox data in the hybrid environment, see [on-premises mailboxes using Outlook for iOS and Android with hybrid Modern Authentication](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth).</span></span>

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="3d85c-171">Где *MailUserIdParameter* указывает пользователя почты (также известного как пользователь с включенной почтой).</span><span class="sxs-lookup"><span data-stu-id="3d85c-171">Where *MailUserIdParameter* specifies a mail user (also known as a mail-enabled user).</span></span> <span data-ttu-id="3d85c-172">Дополнительные сведения о Set-MailUser см. в [списке Set-MailUser.](/powershell/module/exchange/set-mailuser)</span><span class="sxs-lookup"><span data-stu-id="3d85c-172">For more information about the Set-MailUser cmdlet, see [Set-MailUser](/powershell/module/exchange/set-mailuser).</span></span>

## <a name="create-a-dep-for-use-with-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="3d85c-173">Создание deP для использования с SharePoint Online, OneDrive для бизнеса и Teams файлами</span><span class="sxs-lookup"><span data-stu-id="3d85c-173">Create a DEP for use with SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="3d85c-174">Перед началом работы убедитесь, что вы выполнили задачи, необходимые для набора хранилища ключей Azure.</span><span class="sxs-lookup"><span data-stu-id="3d85c-174">Before you begin, ensure that you've completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="3d85c-175">Сведения см. в [перенастройка клиентского ключа](customer-key-set-up.md).</span><span class="sxs-lookup"><span data-stu-id="3d85c-175">For information, see [Set up Customer Key](customer-key-set-up.md).</span></span>
  
<span data-ttu-id="3d85c-176">Чтобы настроить клиентский ключ для SharePoint Online, OneDrive для бизнеса и Teams, выполните эти действия, удаленно подключившись к SharePoint Online с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3d85c-176">To set up Customer Key for SharePoint Online, OneDrive for Business, and Teams files you complete these steps by remotely connecting to SharePoint Online with Windows PowerShell.</span></span>
  
<span data-ttu-id="3d85c-177">Вы связываете deP с набором ключей, хранимых в хранилище ключей Azure.</span><span class="sxs-lookup"><span data-stu-id="3d85c-177">You associate a DEP with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="3d85c-178">Для всех данных в одном географическом расположении, называемом также гео, применяется deP.</span><span class="sxs-lookup"><span data-stu-id="3d85c-178">You apply a DEP to all of your data in one geographic location, also called a geo.</span></span> <span data-ttu-id="3d85c-179">Если вы используете функцию multi-geo Office 365, можно создать один DEP на один гео с возможностью использования различных ключей для каждого гео.</span><span class="sxs-lookup"><span data-stu-id="3d85c-179">If you use the multi-geo feature of Office 365, you can create one DEP per geo with the capability to use different keys per geo.</span></span> <span data-ttu-id="3d85c-180">Если вы не используете multi-geo, вы можете создать один DEP в вашей организации для использования с SharePoint Online, OneDrive для бизнеса и Teams файлами.</span><span class="sxs-lookup"><span data-stu-id="3d85c-180">If you aren't using multi-geo, you can create one DEP in your organization for use with SharePoint Online, OneDrive for Business, and Teams files.</span></span> <span data-ttu-id="3d85c-181">Microsoft 365 для шифрования данных в этом географе используются ключи, выявленные в deP.</span><span class="sxs-lookup"><span data-stu-id="3d85c-181">Microsoft 365 uses the keys identified in the DEP to encrypt your data in that geo.</span></span> <span data-ttu-id="3d85c-182">Чтобы создать DEP, вам нужны URL-адреса key Vault, полученные во время установки.</span><span class="sxs-lookup"><span data-stu-id="3d85c-182">To create the DEP, you need the Key Vault URIs you obtained during setup.</span></span> <span data-ttu-id="3d85c-183">Сведения см. в [элементе Получение URI для каждого ключа Azure Key Vault.](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)</span><span class="sxs-lookup"><span data-stu-id="3d85c-183">For information, see [Obtain the URI for each Azure Key Vault key](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span></span>
  
<span data-ttu-id="3d85c-184">Помните!</span><span class="sxs-lookup"><span data-stu-id="3d85c-184">Remember!</span></span> <span data-ttu-id="3d85c-185">При создании DEP укажите два ключа в двух разных хранилищах ключей Azure.</span><span class="sxs-lookup"><span data-stu-id="3d85c-185">When you create a DEP, you specify two keys in two different Azure Key Vaults.</span></span> <span data-ttu-id="3d85c-186">Создайте эти клавиши в двух отдельных регионах Azure для обеспечения избыточности геоизбытки.</span><span class="sxs-lookup"><span data-stu-id="3d85c-186">Create these keys in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="3d85c-187">Чтобы создать deP, необходимо удаленно подключиться к SharePoint Online с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3d85c-187">To create a DEP, you need to remotely connect to SharePoint Online by using Windows PowerShell.</span></span>
  
1. <span data-ttu-id="3d85c-188">На локальном компьютере с помощью учетной записи работы или школы, которая имеет глобальные разрешения администратора в организации, Подключение SharePoint [Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="3d85c-188">On your local computer, using a work or school account that has global administrator permissions in your organization, [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps).</span></span>

2. <span data-ttu-id="3d85c-189">В Microsoft Office SharePoint Online управленческой оболочки выполните Register-SPODataEncryptionPolicy следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3d85c-189">In the Microsoft SharePoint Online Management Shell, run the Register-SPODataEncryptionPolicy cmdlet as follows:</span></span>

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <adminSiteCollectionURL> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   <span data-ttu-id="3d85c-190">Пример:</span><span class="sxs-lookup"><span data-stu-id="3d85c-190">Example:</span></span>
  
   ```powershell
   Register-SPODataEncryptionPolicy -Identity https://contoso.sharepoint.com -PrimaryKeyVaultName 'stageRG3vault' -PrimaryKeyName 'SPKey3' -PrimaryKeyVersion 'f635a23bd4a44b9996ff6aadd88d42ba' -SecondaryKeyVaultName 'stageRG5vault' -SecondaryKeyName 'SPKey5' -SecondaryKeyVersion '2b3e8f1d754f438dacdec1f0945f251a’
   ```

   <span data-ttu-id="3d85c-191">При регистрации deP шифрование начинается с данных в гео.</span><span class="sxs-lookup"><span data-stu-id="3d85c-191">When you register the DEP, encryption begins on the data in the geo.</span></span> <span data-ttu-id="3d85c-192">Шифрование может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="3d85c-192">Encryption can take some time.</span></span> <span data-ttu-id="3d85c-193">Дополнительные сведения об использовании этого параметра см. в [сайте Register-SPODataEncryptionPolicy.](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="3d85c-193">For more information on using this parameter, see [Register-SPODataEncryptionPolicy](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps).</span></span>

### <a name="view-the-deps-youve-created-for-exchange-online-mailboxes"></a><span data-ttu-id="3d85c-194">Просмотр dePs, созданных для Exchange Online почтовых ящиков</span><span class="sxs-lookup"><span data-stu-id="3d85c-194">View the DEPs you've created for Exchange Online mailboxes</span></span>

<span data-ttu-id="3d85c-195">Чтобы просмотреть список всех созданных для почтовых ящиков dePs, используйте Get-DataEncryptionPolicy PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3d85c-195">To view a list of all the DEPs you've created for mailboxes, use the Get-DataEncryptionPolicy PowerShell cmdlet.</span></span>

1. <span data-ttu-id="3d85c-196">С помощью учетной записи работы или школы, которая имеет глобальные разрешения администратора в вашей организации, подключите Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="3d85c-196">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="3d85c-197">Чтобы вернуть все dePs в организации, запустите Get-DataEncryptionPolicy без параметров.</span><span class="sxs-lookup"><span data-stu-id="3d85c-197">To return all DEPs in your organization, run the Get-DataEncryptionPolicy cmdlet without any parameters.</span></span>

   ```powershell
   Get-DataEncryptionPolicy
   ```

   <span data-ttu-id="3d85c-198">Дополнительные сведения о Get-DataEncryptionPolicy см. в этой записи [в get-DataEncryptionPolicy.](/powershell/module/exchange/get-dataencryptionpolicy)</span><span class="sxs-lookup"><span data-stu-id="3d85c-198">For more information about the Get-DataEncryptionPolicy cmdlet, see [Get-DataEncryptionPolicy](/powershell/module/exchange/get-dataencryptionpolicy).</span></span>

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a><span data-ttu-id="3d85c-199">Назначение deP перед переносом почтового ящика в облако</span><span class="sxs-lookup"><span data-stu-id="3d85c-199">Assign a DEP before you migrate a mailbox to the cloud</span></span>

<span data-ttu-id="3d85c-200">При назначении deP Microsoft 365 шифрует содержимое почтового ящика с помощью назначенного deP во время миграции.</span><span class="sxs-lookup"><span data-stu-id="3d85c-200">When you assign the DEP, Microsoft 365 encrypts the contents of the mailbox using the assigned DEP during the migration.</span></span> <span data-ttu-id="3d85c-201">Этот процесс более эффективен, чем перенос почтового ящика, назначение deP и ожидание шифрования, которое может занять несколько часов или, возможно, дней.</span><span class="sxs-lookup"><span data-stu-id="3d85c-201">This process is more efficient than migrating the mailbox, assigning the DEP, and then waiting for encryption to take place, which can take hours or possibly days.</span></span>

<span data-ttu-id="3d85c-202">Чтобы назначить deP почтовому ящику перед переносом Office 365, запустите Set-MailUser в Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3d85c-202">To assign a DEP to a mailbox before you migrate it to Office 365, run the Set-MailUser cmdlet in Exchange Online PowerShell:</span></span>

1. <span data-ttu-id="3d85c-203">С помощью учетной записи работы или школы, которая имеет глобальные разрешения администратора в вашей организации, подключите Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="3d85c-203">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="3d85c-204">Запустите Set-MailUser.</span><span class="sxs-lookup"><span data-stu-id="3d85c-204">Run the Set-MailUser cmdlet.</span></span>

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   <span data-ttu-id="3d85c-205">Если *GeneralMailboxOrMailUserIdParameter* указывает почтовый ящик, а *DataEncryptionPolicyIdParameter* — это ID deP.</span><span class="sxs-lookup"><span data-stu-id="3d85c-205">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox, and *DataEncryptionPolicyIdParameter* is the ID of the DEP.</span></span> <span data-ttu-id="3d85c-206">Дополнительные сведения о Set-MailUser см. в [списке Set-MailUser.](/powershell/module/exchange/set-mailuser)</span><span class="sxs-lookup"><span data-stu-id="3d85c-206">For more information about the Set-MailUser cmdlet, see [Set-MailUser](/powershell/module/exchange/set-mailuser).</span></span>

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="3d85c-207">Определение deP, назначенного почтовому ящику</span><span class="sxs-lookup"><span data-stu-id="3d85c-207">Determine the DEP assigned to a mailbox</span></span>

<span data-ttu-id="3d85c-208">Чтобы определить deP, назначенное почтовому ящику, используйте Get-MailboxStatistics.</span><span class="sxs-lookup"><span data-stu-id="3d85c-208">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet.</span></span> <span data-ttu-id="3d85c-209">В этом кодлете возвращается уникальный идентификатор (GUID).</span><span class="sxs-lookup"><span data-stu-id="3d85c-209">The cmdlet returns a unique identifier (GUID).</span></span>
  
1. <span data-ttu-id="3d85c-210">С помощью учетной записи работы или школы, которая имеет глобальные разрешения администратора в вашей организации, подключите Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="3d85c-210">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   <span data-ttu-id="3d85c-211">Если *GeneralMailboxOrMailUserIdParameter* указывает почтовый ящик, а DataEncryptionPolicyID возвращает GUID deP.</span><span class="sxs-lookup"><span data-stu-id="3d85c-211">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox and DataEncryptionPolicyID returns the GUID of the DEP.</span></span> <span data-ttu-id="3d85c-212">Дополнительные сведения о Get-MailboxStatistics см. в [списке Get-MailboxStatistics.](/powershell/module/exchange/get-mailboxstatistics)</span><span class="sxs-lookup"><span data-stu-id="3d85c-212">For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](/powershell/module/exchange/get-mailboxstatistics).</span></span>
  
2. <span data-ttu-id="3d85c-213">Запустите Get-DataEncryptionPolicy, чтобы узнать удобное имя deP, которому назначен почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="3d85c-213">Run the Get-DataEncryptionPolicy cmdlet to find out the friendly name of the DEP to which the mailbox is assigned.</span></span>
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   <span data-ttu-id="3d85c-214">Если *GUID* — это GUID, возвращаемая Get-MailboxStatistics на предыдущем этапе.</span><span class="sxs-lookup"><span data-stu-id="3d85c-214">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span>

## <a name="verify-that-customer-key-has-finished-encryption"></a><span data-ttu-id="3d85c-215">Убедитесь, что ключ клиента завершил шифрование</span><span class="sxs-lookup"><span data-stu-id="3d85c-215">Verify that Customer Key has finished encryption</span></span>

<span data-ttu-id="3d85c-216">Вне зависимости от того, были ли вы свернут ключ клиента, назначен новый deP или перенесен почтовый ящик, используйте действия в этом разделе для обеспечения завершения шифрования.</span><span class="sxs-lookup"><span data-stu-id="3d85c-216">Whether you've rolled a Customer Key, assigned a new DEP, or migrated a mailbox, use the steps in this section to ensure that encryption completes.</span></span>

### <a name="verify-encryption-completes-for-exchange-online-mailboxes"></a><span data-ttu-id="3d85c-217">Проверка завершения шифрования для Exchange Online почтовых ящиков</span><span class="sxs-lookup"><span data-stu-id="3d85c-217">Verify encryption completes for Exchange Online mailboxes</span></span>

<span data-ttu-id="3d85c-218">Шифрование почтового ящика может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="3d85c-218">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="3d85c-219">При первом шифровании почтовый ящик должен полностью перемещаться из одной базы данных в другую, прежде чем служба сможет шифровать почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="3d85c-219">For first time encryption, the mailbox must also completely move from one database to another before the service can encrypt the mailbox.</span></span>
  
<span data-ttu-id="3d85c-220">Используйте Get-MailboxStatistics, чтобы определить, зашифрован ли почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="3d85c-220">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="3d85c-221">Свойство IsEncrypted возвращает значение  true, если почтовый ящик зашифрован, и значение **false,** если почтовый ящик не зашифрован.</span><span class="sxs-lookup"><span data-stu-id="3d85c-221">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox isn't encrypted.</span></span> <span data-ttu-id="3d85c-222">Время выполнения ходов почтовых ящиков зависит от количества почтовых ящиков, которым вы назначаете deP впервые, и размера почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="3d85c-222">The time to complete mailbox moves depends on the number of mailboxes to which you assign a DEP for the first time, and the size of the mailboxes.</span></span> <span data-ttu-id="3d85c-223">Если почтовые ящики не были зашифрованы через неделю с того времени, как вы назначены deP, обратитесь в Корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3d85c-223">If the mailboxes haven't been encrypted after a week from the time you assigned the DEP, contact Microsoft.</span></span>

<span data-ttu-id="3d85c-224">Этот New-MoveRequest больше не доступен для перемещения локальных почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="3d85c-224">The New-MoveRequest cmdlet is no longer available for local mailbox moves.</span></span> <span data-ttu-id="3d85c-225">Дополнительные [сведения можно найти в](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) этом объявлении.</span><span class="sxs-lookup"><span data-stu-id="3d85c-225">Refer to [this announcement](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) for additional information.</span></span>

### <a name="verify-encryption-completes-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="3d85c-226">Проверка завершения шифрования для SharePoint, OneDrive для бизнеса и Teams файлов</span><span class="sxs-lookup"><span data-stu-id="3d85c-226">Verify encryption completes for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="3d85c-227">Проверьте состояние шифрования, запуская Get-SPODataEncryptionPolicy следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3d85c-227">Check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

```PowerShell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="3d85c-228">Выход из этого комлета включает в себя:</span><span class="sxs-lookup"><span data-stu-id="3d85c-228">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="3d85c-229">URI основного ключа.</span><span class="sxs-lookup"><span data-stu-id="3d85c-229">The URI of the primary key.</span></span>

- <span data-ttu-id="3d85c-230">URI вторичного ключа.</span><span class="sxs-lookup"><span data-stu-id="3d85c-230">The URI of the secondary key.</span></span>

- <span data-ttu-id="3d85c-231">Состояние шифрования для гео.</span><span class="sxs-lookup"><span data-stu-id="3d85c-231">The encryption status for the geo.</span></span> <span data-ttu-id="3d85c-232">Возможные состояния:</span><span class="sxs-lookup"><span data-stu-id="3d85c-232">Possible states include:</span></span>

  - <span data-ttu-id="3d85c-233">**Незарегистрированные:** Шифрование ключа клиента еще не применено.</span><span class="sxs-lookup"><span data-stu-id="3d85c-233">**Unregistered:** Customer Key encryption has not yet been applied.</span></span>

  - <span data-ttu-id="3d85c-234">**Регистрация:** Шифрование ключа клиента было применено, и ваши файлы находятся в процессе шифрования.</span><span class="sxs-lookup"><span data-stu-id="3d85c-234">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted.</span></span> <span data-ttu-id="3d85c-235">Если ключ для георегистра регистрируется, вам также будет показана информация о том, какой процент сайтов в геополии завершен, чтобы можно было отслеживать ход шифрования.</span><span class="sxs-lookup"><span data-stu-id="3d85c-235">If the key for the geo is registering, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span>

  - <span data-ttu-id="3d85c-236">**Зарегистрированы:** Было применено шифрование ключа клиента, и все файлы на всех сайтах были зашифрованы.</span><span class="sxs-lookup"><span data-stu-id="3d85c-236">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span>

  - <span data-ttu-id="3d85c-237">**Прокатка:** В настоящее время продолжается перекат ключей.</span><span class="sxs-lookup"><span data-stu-id="3d85c-237">**Rolling:** A key roll is in progress.</span></span> <span data-ttu-id="3d85c-238">Если ключ для геоската катится, вам также будет показана информация о том, какой процент сайтов завершил операцию рулона ключа, чтобы можно было отслеживать ход выполнения.</span><span class="sxs-lookup"><span data-stu-id="3d85c-238">If the key for the geo is rolling, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span>

## <a name="get-details-about-deps-you-use-with-multiple-workloads"></a><span data-ttu-id="3d85c-239">Сведения об использовании dePs с несколькими рабочими нагрузками</span><span class="sxs-lookup"><span data-stu-id="3d85c-239">Get details about DEPs you use with multiple workloads</span></span>

<span data-ttu-id="3d85c-240">Чтобы получить сведения обо всех созданных для использования dePs с несколькими рабочими нагрузками, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="3d85c-240">To get details about all of the DEPs you've created to use with multiple workloads, complete these steps:</span></span>

1. <span data-ttu-id="3d85c-241">На локальном компьютере с помощью учетной записи работы или учебного заведения с разрешениями администратора глобального администратора или администратора соответствия требованиям подключайтесь к Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) в Windows PowerShell окне.</span><span class="sxs-lookup"><span data-stu-id="3d85c-241">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

   - <span data-ttu-id="3d85c-242">Чтобы вернуть список всех многопрофильных dePs в организации, запустите эту команду.</span><span class="sxs-lookup"><span data-stu-id="3d85c-242">To return the list of all multi-workload DEPs in the organization, run this command.</span></span>

     ```powershell
        Get-M365DataAtRestEncryptionPolicy
     ```

   - <span data-ttu-id="3d85c-243">Чтобы вернуть сведения о конкретном deP, запустите эту команду.</span><span class="sxs-lookup"><span data-stu-id="3d85c-243">To return details about a specific DEP, run this command.</span></span> <span data-ttu-id="3d85c-244">В этом примере возвращается подробная информация для deP с именем "Contoso_Global".</span><span class="sxs-lookup"><span data-stu-id="3d85c-244">This example returns detailed information for the DEP named "Contoso_Global".</span></span>

     ```powershell
        Get-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global"
     ```

## <a name="get-multi-workload-dep-assignment-information"></a><span data-ttu-id="3d85c-245">Получить сведения о назначении deP с несколькими рабочими нагрузками</span><span class="sxs-lookup"><span data-stu-id="3d85c-245">Get multi-workload DEP assignment information</span></span>

<span data-ttu-id="3d85c-246">Чтобы узнать, какой deP в настоящее время назначен вашему клиенту, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="3d85c-246">To find out which DEP is currently assigned to your tenant, follow these steps.</span></span> 

1. <span data-ttu-id="3d85c-247">На локальном компьютере с помощью учетной записи работы или учебного заведения с разрешениями администратора глобального администратора или администратора соответствия требованиям подключайтесь к Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) в Windows PowerShell окне.</span><span class="sxs-lookup"><span data-stu-id="3d85c-247">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="3d85c-248">Введите эту команду.</span><span class="sxs-lookup"><span data-stu-id="3d85c-248">Type this command.</span></span>

   ```powershell
      Get-M365DataAtRestEncryptionPolicyAssignment
   ```

## <a name="disable-a-multi-workload-dep"></a><span data-ttu-id="3d85c-249">Отключение deP с несколькими рабочими нагрузками</span><span class="sxs-lookup"><span data-stu-id="3d85c-249">Disable a multi-workload DEP</span></span>

<span data-ttu-id="3d85c-250">Прежде чем отключить deP с несколькими рабочими нагрузками, отключите deP от рабочих нагрузок в клиенте.</span><span class="sxs-lookup"><span data-stu-id="3d85c-250">Before you disable a multi-workload DEP, unassign the DEP from workloads in your tenant.</span></span> <span data-ttu-id="3d85c-251">Чтобы отключить deP, используемый с несколькими рабочими нагрузками, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="3d85c-251">To disable a DEP used with multiple workloads, complete these steps:</span></span>

1. <span data-ttu-id="3d85c-252">На локальном компьютере с помощью учетной записи работы или учебного заведения с разрешениями администратора глобального администратора или администратора соответствия требованиям подключайтесь к Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) в Windows PowerShell окне.</span><span class="sxs-lookup"><span data-stu-id="3d85c-252">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="3d85c-253">Запустите Set-M365DataAtRestEncryptionPolicy.</span><span class="sxs-lookup"><span data-stu-id="3d85c-253">Run the Set-M365DataAtRestEncryptionPolicy cmdlet.</span></span>
  
   ```powershell
   Set-M365DataAtRestEncryptionPolicy -[Identity] "PolicyName" -Enabled $false
   ```

<span data-ttu-id="3d85c-254">Где *PolicyName* — это имя или уникальный ID политики.</span><span class="sxs-lookup"><span data-stu-id="3d85c-254">Where *PolicyName* is the name or unique ID of the policy.</span></span> <span data-ttu-id="3d85c-255">Например, Contoso_Global.</span><span class="sxs-lookup"><span data-stu-id="3d85c-255">For example, Contoso_Global.</span></span>

<span data-ttu-id="3d85c-256">Пример:</span><span class="sxs-lookup"><span data-stu-id="3d85c-256">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global" -Enabled $false
```

## <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="3d85c-257">Восстановление ключей Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="3d85c-257">Restore Azure Key Vault keys</span></span>

<span data-ttu-id="3d85c-258">Перед выполнением восстановления используйте возможности восстановления, предоставляемые мягким удалением.</span><span class="sxs-lookup"><span data-stu-id="3d85c-258">Before performing a restore, use the recovery capabilities provided by soft delete.</span></span> <span data-ttu-id="3d85c-259">Для всех ключей, используемых с ключом клиента, требуется включить мягкое удаление.</span><span class="sxs-lookup"><span data-stu-id="3d85c-259">All keys that are used with Customer Key are required to have soft delete enabled.</span></span> <span data-ttu-id="3d85c-260">Мягкое удаление действует как корзина для переработки и позволяет восстанавливать до 90 дней без необходимости восстановления.</span><span class="sxs-lookup"><span data-stu-id="3d85c-260">Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore.</span></span> <span data-ttu-id="3d85c-261">Восстановление должно требоваться только в экстремальных или необычных обстоятельствах, например, если ключ или хранилище ключа потеряно.</span><span class="sxs-lookup"><span data-stu-id="3d85c-261">Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost.</span></span> <span data-ttu-id="3d85c-262">Если необходимо восстановить ключ для использования с ключом клиента, в Azure PowerShell выполните Restore-AzureKeyVaultKey следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3d85c-262">If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

<span data-ttu-id="3d85c-263">Например:</span><span class="sxs-lookup"><span data-stu-id="3d85c-263">For example:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="3d85c-264">Если хранилище ключей уже содержит ключ с тем же именем, операция восстановления сбой.</span><span class="sxs-lookup"><span data-stu-id="3d85c-264">If the key vault already contains a key with the same name, the restore operation fails.</span></span> <span data-ttu-id="3d85c-265">Restore-AzKeyVaultKey восстанавливает все ключевые версии и все метаданные для ключа, включая имя ключа.</span><span class="sxs-lookup"><span data-stu-id="3d85c-265">Restore-AzKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
## <a name="manage-key-vault-permissions"></a><span data-ttu-id="3d85c-266">Управление разрешениями хранилища ключей</span><span class="sxs-lookup"><span data-stu-id="3d85c-266">Manage key vault permissions</span></span>

<span data-ttu-id="3d85c-267">Доступно несколько cmdlets, которые позволяют просматривать и при необходимости удалять разрешения на хранилище ключей.</span><span class="sxs-lookup"><span data-stu-id="3d85c-267">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions.</span></span> <span data-ttu-id="3d85c-268">Может потребоваться удалить разрешения, например, когда сотрудник покидает команду.</span><span class="sxs-lookup"><span data-stu-id="3d85c-268">You might need to remove permissions, for example, when an employee leaves the team.</span></span> <span data-ttu-id="3d85c-269">Для каждой из этих задач вы будете использовать Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3d85c-269">For each of these tasks, you will use Azure PowerShell.</span></span> <span data-ttu-id="3d85c-270">Сведения о Azure PowerShell см. в [обзоре Azure PowerShell.](/powershell/azure/)</span><span class="sxs-lookup"><span data-stu-id="3d85c-270">For information about Azure PowerShell, see [Overview of Azure PowerShell](/powershell/azure/).</span></span>

<span data-ttu-id="3d85c-271">Чтобы просмотреть разрешения хранилища ключей, запустите Get-AzKeyVault.</span><span class="sxs-lookup"><span data-stu-id="3d85c-271">To view key vault permissions, run the Get-AzKeyVault cmdlet.</span></span>

```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="3d85c-272">Например:</span><span class="sxs-lookup"><span data-stu-id="3d85c-272">For example:</span></span>

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="3d85c-273">Чтобы удалить разрешения администратора, запустите Remove-AzKeyVaultAccessPolicy:</span><span class="sxs-lookup"><span data-stu-id="3d85c-273">To remove an administrator's permissions, run the Remove-AzKeyVaultAccessPolicy cmdlet:</span></span>
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

<span data-ttu-id="3d85c-274">Например:</span><span class="sxs-lookup"><span data-stu-id="3d85c-274">For example:</span></span>

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="roll-back-from-customer-key-to-microsoft-managed-keys"></a><span data-ttu-id="3d85c-275">Откат от ключа клиента к управляемым клавишам Майкрософт</span><span class="sxs-lookup"><span data-stu-id="3d85c-275">Roll back from Customer Key to Microsoft managed Keys</span></span>

<span data-ttu-id="3d85c-276">Если вам нужно вернуться к клавишам с управлением Майкрософт, вы можете.</span><span class="sxs-lookup"><span data-stu-id="3d85c-276">If you need to revert to Microsoft-managed keys, you can.</span></span> <span data-ttu-id="3d85c-277">При отключении данные повторно шифруются с помощью шифрования по умолчанию, поддерживаемого каждой отдельной рабочей нагрузкой.</span><span class="sxs-lookup"><span data-stu-id="3d85c-277">When you offboard, your data is re-encrypted using default encryption supported by each individual workload.</span></span> <span data-ttu-id="3d85c-278">Например, Exchange Online шифрование по умолчанию с помощью управляемых Microsoft ключей.</span><span class="sxs-lookup"><span data-stu-id="3d85c-278">For example, Exchange Online supports default encryption using Microsoft-managed keys.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3d85c-279">Offboarding — это не то же самое, что очистка данных.</span><span class="sxs-lookup"><span data-stu-id="3d85c-279">Offboarding is not the same as a data purge.</span></span> <span data-ttu-id="3d85c-280">Очистка данных навсегда удаляет данные вашей организации из Microsoft 365, offboarding этого не делает.</span><span class="sxs-lookup"><span data-stu-id="3d85c-280">A data purge permanently crypto-deletes your organization's data from Microsoft 365, offboarding does not.</span></span> <span data-ttu-id="3d85c-281">Вы не можете выполнить очистку данных для нескольких политик рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="3d85c-281">You can't perform a data purge for a multiple workload policy.</span></span>

<span data-ttu-id="3d85c-282">Если вы решите больше не использовать клиентский ключ для назначения депов с несколькими рабочими нагрузками, вам потребуется связаться с поддержкой Майкрософт с запросом на "отключение" от ключа клиента.</span><span class="sxs-lookup"><span data-stu-id="3d85c-282">If you decide not to use Customer Key for assigning multi-workload DEPs anymore then you'll need to reach out to Microsoft support with a request to “offboard” from Customer Key.</span></span> <span data-ttu-id="3d85c-283">Попросите команду поддержки подать запрос на службу Microsoft 365 клиента.</span><span class="sxs-lookup"><span data-stu-id="3d85c-283">Ask the support team to file a service request against Microsoft 365 Customer Key team.</span></span> <span data-ttu-id="3d85c-284">Связаться с m365-ck@service.microsoft.com, если у вас есть какие-либо вопросы.</span><span class="sxs-lookup"><span data-stu-id="3d85c-284">Reach out to m365-ck@service.microsoft.com if you have any questions.</span></span>

<span data-ttu-id="3d85c-285">Если вы больше не хотите шифровать отдельные почтовые ящики с помощью dePs уровня почтовых ящиков, можно отогнать dePs уровня почтовых ящиков из всех почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="3d85c-285">If you do not want to encrypt individual mailboxes using mailbox level DEPs anymore, then you can unassign mailbox level DEPs from all your mailboxes.</span></span>

<span data-ttu-id="3d85c-286">Чтобы отогнать dePs почтового ящика, используйте Set-Mailbox PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3d85c-286">To unassign mailbox DEPs, use the Set-Mailbox PowerShell cmdlet.</span></span>

1. <span data-ttu-id="3d85c-287">С помощью учетной записи работы или школы, которая имеет глобальные разрешения администратора в вашей организации, подключите Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="3d85c-287">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="3d85c-288">Запустите Set-Mailbox.</span><span class="sxs-lookup"><span data-stu-id="3d85c-288">Run the Set-Mailbox cmdlet.</span></span>

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

<span data-ttu-id="3d85c-289">При запуске этого cmdlet открепит назначенное в настоящее время deP и повторно зашифровка почтового ящика с помощью DEP, связанного с ключами microsoft-managed по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3d85c-289">Running this cmdlet unassigns the currently assigned DEP and reencrypts the mailbox using the DEP associated with default Microsoft-managed keys.</span></span> <span data-ttu-id="3d85c-290">Нельзя отоименить deP, используемый управляемыми ключами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3d85c-290">You can't unassign the DEP used by Microsoft managed keys.</span></span> <span data-ttu-id="3d85c-291">Если вы не хотите использовать ключи с управлением Майкрософт, вы можете назначить в почтовый ящик другой DEP ключа клиента.</span><span class="sxs-lookup"><span data-stu-id="3d85c-291">If you don't want to use Microsoft-managed keys, you can assign another Customer Key DEP to the mailbox.</span></span>

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a><span data-ttu-id="3d85c-292">Отзовите ключи и запустите процесс очистки данных</span><span class="sxs-lookup"><span data-stu-id="3d85c-292">Revoke your keys and start the data purge path process</span></span>

<span data-ttu-id="3d85c-293">Вы контролируете отзыв всех корневых ключей, включая ключ доступности.</span><span class="sxs-lookup"><span data-stu-id="3d85c-293">You control the revocation of all root keys including the availability key.</span></span> <span data-ttu-id="3d85c-294">Ключ клиента обеспечивает контроль за аспектом планирования выхода из системы нормативных требований для вас.</span><span class="sxs-lookup"><span data-stu-id="3d85c-294">Customer Key provides control of the exit planning aspect of the regulatory requirements for you.</span></span> <span data-ttu-id="3d85c-295">Если вы решите отопустить ключи для очистки данных и выхода из службы, служба удаляет ключ доступности после завершения процесса очистки данных.</span><span class="sxs-lookup"><span data-stu-id="3d85c-295">If you decide to revoke your keys to purge your data and exit the service, the service deletes the availability key once the data purge process completes.</span></span> <span data-ttu-id="3d85c-296">Это поддерживается для dePs ключа клиента, которые назначены отдельным почтовым ящикам.</span><span class="sxs-lookup"><span data-stu-id="3d85c-296">This is supported for Customer Key DEPs that are assigned to individual mailboxes.</span></span>

<span data-ttu-id="3d85c-297">Microsoft 365 аудит и проверяет путь очистки данных.</span><span class="sxs-lookup"><span data-stu-id="3d85c-297">Microsoft 365 audits and validates the data purge path.</span></span> <span data-ttu-id="3d85c-298">Дополнительные сведения см. в отчете SSAE 18 SOC 2, доступном на [портале доверия к службам.](https://servicetrust.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="3d85c-298">For more information, see the SSAE 18 SOC 2 Report available on the [Service Trust Portal](https://servicetrust.microsoft.com/).</span></span> <span data-ttu-id="3d85c-299">Кроме того, Корпорация Майкрософт рекомендует следующие документы:</span><span class="sxs-lookup"><span data-stu-id="3d85c-299">In addition, Microsoft recommends the following documents:</span></span>

- [<span data-ttu-id="3d85c-300">Руководство по оценке рисков и обеспечению соответствия требованиям для финансовых учреждений в Облаке Майкрософт</span><span class="sxs-lookup"><span data-stu-id="3d85c-300">Risk Assessment and Compliance Guide for Financial Institutions in the Microsoft Cloud</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [<span data-ttu-id="3d85c-301">Соображения планирования выхода O365</span><span class="sxs-lookup"><span data-stu-id="3d85c-301">O365 Exit Planning Considerations</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

<span data-ttu-id="3d85c-302">Purging of multi-workload DEP is not supported for Microsoft 365 Customer Key.</span><span class="sxs-lookup"><span data-stu-id="3d85c-302">Purging of multi-workload DEP is not supported for Microsoft 365 Customer Key.</span></span> <span data-ttu-id="3d85c-303">DeP с несколькими рабочими нагрузками используется для шифрования данных между несколькими рабочими нагрузками для всех пользователей-клиентов.</span><span class="sxs-lookup"><span data-stu-id="3d85c-303">The multi-workload DEP is used to encrypt data across multiple workloads across all tenant users.</span></span> <span data-ttu-id="3d85c-304">Чистка таких deP приведет к недоступности данных из нескольких рабочих нагрузок.</span><span class="sxs-lookup"><span data-stu-id="3d85c-304">Purging such DEP would result into data from across multiple workloads become inaccessible.</span></span> <span data-ttu-id="3d85c-305">Если вы решите полностью Microsoft 365 службы, можно продолжить путь удаления клиента в документированном процессе.</span><span class="sxs-lookup"><span data-stu-id="3d85c-305">If you decide to exit Microsoft 365 services altogether then you could pursue the path of tenant deletion per the documented process.</span></span> <span data-ttu-id="3d85c-306">Узнайте, [как удалить клиента в Azure Active Directoy.](/azure/active-directory/enterprise-users/directory-delete-howto)</span><span class="sxs-lookup"><span data-stu-id="3d85c-306">See [how to delete a tenant in Azure Active Directoy](/azure/active-directory/enterprise-users/directory-delete-howto).</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="3d85c-307">Отзовите ключи клиента и ключ доступности для Exchange Online и Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="3d85c-307">Revoke your Customer Keys and the availability key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="3d85c-308">Когда вы инициируете путь очистки данных для Exchange Online и Skype для бизнеса, вы установите постоянный запрос очистки данных на deP.</span><span class="sxs-lookup"><span data-stu-id="3d85c-308">When you initiate the data purge path for Exchange Online and Skype for Business, you set a permanent data purge request on a DEP.</span></span> <span data-ttu-id="3d85c-309">Это навсегда удаляет зашифрованные данные в почтовых ящиках, которым назначен этот deP.</span><span class="sxs-lookup"><span data-stu-id="3d85c-309">Doing so permanently deletes encrypted data within the mailboxes to which that DEP is assigned.</span></span>

<span data-ttu-id="3d85c-310">Так как вы можете запускать только комдлет PowerShell по одному deP одновременно, перед началом пути очистки данных рассмотрите возможность повторного перенанаружания единого deP для всех почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="3d85c-310">Since you can only run the PowerShell cmdlet against one DEP at a time, consider reassigning a single DEP to all of your mailboxes before you initiate the data purge path.</span></span>

> [!WARNING]
> <span data-ttu-id="3d85c-311">Не используйте путь очистки данных для удаления подмножество почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="3d85c-311">Do not use the data purge path to delete a subset of your mailboxes.</span></span> <span data-ttu-id="3d85c-312">Этот процесс предназначен только для клиентов, которые выходят из службы.</span><span class="sxs-lookup"><span data-stu-id="3d85c-312">This process is only intended for customers who are exiting the service.</span></span>

<span data-ttu-id="3d85c-313">Чтобы инициировать путь очистки данных, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="3d85c-313">To initiate the data purge path, complete these steps:</span></span>

1. <span data-ttu-id="3d85c-314">Удалите разрешения на обертывание и открутку для "O365 Exchange Online" из хранилища ключей Azure.</span><span class="sxs-lookup"><span data-stu-id="3d85c-314">Remove wrap and unwrap permissions for "O365 Exchange Online" from Azure Key Vaults.</span></span>

2. <span data-ttu-id="3d85c-315">С помощью учетной записи для работы или школы, которая имеет глобальные права администратора в организации, подключите Exchange Online [PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="3d85c-315">Using a work or school account that has global administrator privileges in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

3. <span data-ttu-id="3d85c-316">Для каждого deP, который содержит почтовые ящики, которые необходимо удалить, выполните [набор-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) следующим образом.</span><span class="sxs-lookup"><span data-stu-id="3d85c-316">For each DEP that contains mailboxes that you want to delete, run the [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) cmdlet as follows.</span></span>

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   <span data-ttu-id="3d85c-317">Если команда сбой, убедитесь, что вы удалили Exchange Online с обоих ключей в Хранилище ключей Azure, как указано ранее в этой задаче.</span><span class="sxs-lookup"><span data-stu-id="3d85c-317">If the command fails, ensure that you've removed the Exchange Online permissions from both keys in Azure Key Vault as specified earlier in this task.</span></span><span data-ttu-id="3d85c-318">После того как вы установите переключатель PermanentDataPurgeRequested с помощью Set-DataEncryptionPolicy, вы больше не сможете назначить этот deP почтовым ящикам.</span><span class="sxs-lookup"><span data-stu-id="3d85c-318"> Once you've set the PermanentDataPurgeRequested switch using the Set-DataEncryptionPolicy cmdlet, you'll no longer be able to assign this DEP to mailboxes.</span></span>

4. <span data-ttu-id="3d85c-319">Обратитесь в службу поддержки Корпорации Майкрософт и запросите eDocument очистки данных.</span><span class="sxs-lookup"><span data-stu-id="3d85c-319">Contact Microsoft support and request the Data Purge eDocument.</span></span>

    <span data-ttu-id="3d85c-320">По вашему запросу Корпорация Майкрософт отправляет вам юридический документ для подтверждения и авторизации удаления данных.</span><span class="sxs-lookup"><span data-stu-id="3d85c-320">At your request, Microsoft sends you a legal document to acknowledge and authorize data deletion.</span></span> <span data-ttu-id="3d85c-321">Человек в вашей организации, который зарегистрировался в качестве утвержденного в предложении FastTrack во время входной регистрации, должен подписать этот документ.</span><span class="sxs-lookup"><span data-stu-id="3d85c-321">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="3d85c-322">Как правило, это руководитель или другое назначенное лицо в вашей компании, которому по закону разрешено подписывать документы от имени вашей организации.</span><span class="sxs-lookup"><span data-stu-id="3d85c-322">Normally, this is an executive or other designated person in your company who is legally authorized to sign the paperwork on behalf of your organization.</span></span>

5. <span data-ttu-id="3d85c-323">После того как ваш представитель подписал юридический документ, верни его в Корпорацию Майкрософт (как правило, с помощью подписи eDoc).</span><span class="sxs-lookup"><span data-stu-id="3d85c-323">Once your representative has signed the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

    <span data-ttu-id="3d85c-324">Когда Корпорация Майкрософт получает юридический документ, Корпорация Майкрософт запускает комлеты, чтобы вызвать очистку данных, которая сначала удаляет политику, отмечает почтовые ящики для постоянного удаления, а затем удаляет ключ доступности.</span><span class="sxs-lookup"><span data-stu-id="3d85c-324">Once Microsoft receives the legal document, Microsoft runs cmdlets to trigger the data purge which first deletes the policy, marks the mailboxes for permanent deletion, then deletes the availability key.</span></span> <span data-ttu-id="3d85c-325">После завершения процесса очистки данных данные будут очищены, недоступны для Exchange Online и не могут быть восстановлены.</span><span class="sxs-lookup"><span data-stu-id="3d85c-325">Once the data purge process completes, the data has been purged, is inaccessible to Exchange Online, and is not recoverable.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="3d85c-326">Отзовите ключи клиента и ключ доступности для SharePoint, OneDrive для бизнеса и Teams файлов</span><span class="sxs-lookup"><span data-stu-id="3d85c-326">Revoke your Customer Keys and the availability key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="3d85c-327">Чтобы инициировать путь очистки данных для SharePoint Online, OneDrive для бизнеса и Teams, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="3d85c-327">To initiate the data purge path for SharePoint Online, OneDrive for Business, and Teams files, complete these steps:</span></span>

1. <span data-ttu-id="3d85c-328">Отзови доступ к хранилищем ключей Azure.</span><span class="sxs-lookup"><span data-stu-id="3d85c-328">Revoke Azure Key Vault access.</span></span> <span data-ttu-id="3d85c-329">Все администраторы хранилища ключей должны согласиться на отвод доступа.</span><span class="sxs-lookup"><span data-stu-id="3d85c-329">All key vault admins must agree to revoke access.</span></span>

   <span data-ttu-id="3d85c-330">Хранилище ключей Azure для SharePoint Online не удаляется.</span><span class="sxs-lookup"><span data-stu-id="3d85c-330">You do not delete the Azure Key Vault for SharePoint Online.</span></span> <span data-ttu-id="3d85c-331">Хранилища ключей могут быть общими для нескольких SharePoint и dePs.</span><span class="sxs-lookup"><span data-stu-id="3d85c-331">Key vaults may be shared among several SharePoint Online tenants and DEPs.</span></span>

2. <span data-ttu-id="3d85c-332">Свяжитесь с Корпорацией Майкрософт, чтобы удалить ключ доступности.</span><span class="sxs-lookup"><span data-stu-id="3d85c-332">Contact Microsoft to delete the availability key.</span></span>

    <span data-ttu-id="3d85c-333">Когда вы обратитесь в Корпорацию Майкрософт, чтобы удалить ключ доступности, мы отправим вам юридический документ.</span><span class="sxs-lookup"><span data-stu-id="3d85c-333">When you contact Microsoft to delete the availability key, we'll send you a legal document.</span></span> <span data-ttu-id="3d85c-334">Человек в вашей организации, который зарегистрировался в качестве утвержденного в предложении FastTrack во время входной регистрации, должен подписать этот документ.</span><span class="sxs-lookup"><span data-stu-id="3d85c-334">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="3d85c-335">Как правило, это руководитель или другой назначенный человек в вашей компании, который имеет юридические права подписывать документы от имени организации.</span><span class="sxs-lookup"><span data-stu-id="3d85c-335">Normally, this is an executive or other designated person in your company who's legally authorized to sign the paperwork on behalf of your organization.</span></span>

3. <span data-ttu-id="3d85c-336">Как только ваш представитель подпишет юридический документ, верни его в Microsoft (обычно с помощью подписи eDoc).</span><span class="sxs-lookup"><span data-stu-id="3d85c-336">Once your representative signs the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

   <span data-ttu-id="3d85c-337">Когда Корпорация Майкрософт получает юридический документ, мы запускаем комлеты, чтобы вызвать очистку данных, которая выполняет крипто-удаление ключа клиента, ключа сайта и всех отдельных ключей каждого документа, безвозвратно нарушая иерархию ключей.</span><span class="sxs-lookup"><span data-stu-id="3d85c-337">Once Microsoft receives the legal document, we run cmdlets to trigger the data purge which performs crypto deletion of the tenant key, site key, and all individual per-document keys, irrevocably breaking the key hierarchy.</span></span> <span data-ttu-id="3d85c-338">После завершения очистки данных данные будут очищены.</span><span class="sxs-lookup"><span data-stu-id="3d85c-338">Once the data purge cmdlets complete, your data has been purged.</span></span>

## <a name="related-articles"></a><span data-ttu-id="3d85c-339">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="3d85c-339">Related articles</span></span>

- [<span data-ttu-id="3d85c-340">Шифрование службы с помощью ключа клиента</span><span class="sxs-lookup"><span data-stu-id="3d85c-340">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="3d85c-341">Узнайте о ключе доступности</span><span class="sxs-lookup"><span data-stu-id="3d85c-341">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="3d85c-342">Настройка ключа клиента</span><span class="sxs-lookup"><span data-stu-id="3d85c-342">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="3d85c-343">Смена или ротация ключа клиента или ключа доступности</span><span class="sxs-lookup"><span data-stu-id="3d85c-343">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="3d85c-344">Защищенное хранилище пользователя</span><span class="sxs-lookup"><span data-stu-id="3d85c-344">Customer Lockbox</span></span>](customer-lockbox-requests.md)

- [<span data-ttu-id="3d85c-345">Шифрование служб</span><span class="sxs-lookup"><span data-stu-id="3d85c-345">Service Encryption</span></span>](office-365-service-encryption.md)