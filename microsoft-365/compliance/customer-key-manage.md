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
# <a name="manage-customer-key"></a>Управление ключом клиента

После создания ключа клиента для Office 365 необходимо создать и назначить одну или несколько политик шифрования данных (DEP). После того как вы направите dePs, вы сможете управлять ключами, как описано в этой статье. Дополнительные данные о ключе клиента в связанных темах.

## <a name="create-a-dep-for-use-with-multiple-workloads-for-all-tenant-users"></a>Создание deP для использования с несколькими рабочими нагрузками для всех пользователей-клиентов

Перед началом работы убедитесь, что вы выполнили задачи, необходимые для набора клиента. Сведения см. в [перенастройка клиентского ключа](customer-key-set-up.md). Чтобы создать DEP, вам нужны URL-адреса key Vault, полученные во время установки. Сведения см. в [элементе Получение URI для каждого ключа Azure Key Vault.](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)

Чтобы создать deP с несколькими рабочими нагрузками, выполните следующие действия:
  
1. На локальном компьютере с помощью учетной записи работы или учебного заведения с разрешениями администратора глобального администратора или администратора соответствия требованиям подключайтесь к Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) в Windows PowerShell окне.

2. Чтобы создать DEP, используйте New-M365DataAtRestEncryptionPolicy.

   ```powershell
   New-M365DataAtRestEncryptionPolicy -Name <PolicyName> -AzureKeyIDs <KeyVaultURI1, KeyVaultURI2> [-Description <String>]
   ```

   Где:

   - *PolicyName* — это имя, которое необходимо использовать для политики. Имена не могут содержать пробелы. Например, Contoso_Global.

   - *KeyVaultURI1* — это URI для первого ключа в политике. Например, <https://contosoWestUSvault1.vault.azure.net/keys/Key_01>.

   - *KeyVaultURI2* — это URI для второго ключа в политике. Например, <https://contosoCentralUSvault1.vault.azure.net/keys/Key_02>. Разделять два URL-адреса на запятую и пробел.

   - *Описание политики* — это удобное описание политики, которое поможет вам вспомнить, для чего нужна политика. В описании можно включить пробелы. Например, "Корневая политика для нескольких рабочих нагрузок для всех пользователей в клиенте".

Пример:

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Contoso_Global" -AzureKeyIDs "https://contosoWestUSvault1.vault.azure.net/keys/Key_01","https://contosoCentralUSvault1.vault.azure.net/keys/Key_02" -Description "Policy for multiple workloads for all users in the tenant."
```

### <a name="assign-multi-workload-policy"></a>Назначение политики с несколькими рабочими нагрузками

Назначение deP с помощью Set-M365DataAtRestEncryptionPolicyAssignment. После назначения политики Microsoft 365 шифровать данные с помощью ключа, идентифицированного в deP.

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy <PolicyName or ID>
```

 Где *PolicyName* — это имя политики. Например, Contoso_Global.

Пример:

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "Contoso_Global"
```

## <a name="create-a-dep-for-use-with-exchange-online-mailboxes"></a>Создание deP для использования с Exchange Online почтовыми ящиками

Перед началом работы убедитесь, что вы выполнили задачи, необходимые для набора хранилища ключей Azure. Сведения см. в [перенастройка клиентского ключа](customer-key-set-up.md). Вы выполните эти действия, удаленно подключившись к Exchange Online с Windows PowerShell.

DeP связан с набором ключей, хранимых в хранилище ключей Azure. Вы назначаете deP почтовому ящику в Microsoft 365. Microsoft 365 затем использовать ключи, выявленные в политике, для шифрования почтового ящика. Чтобы создать DEP, вам нужны URL-адреса key Vault, полученные во время установки. Сведения см. в [элементе Получение URI для каждого ключа Azure Key Vault.](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)

Помните! При создании DEP укажите два ключа в двух разных хранилищах ключей Azure. Создайте эти клавиши в двух отдельных регионах Azure для обеспечения избыточности геоизбытки.

Чтобы создать deP для использования с почтовым ящиком, выполните следующие действия:
  
1. На локальном компьютере с помощью учетной записи работы или учебного заведения с разрешениями глобального администратора или администратора Exchange Online администратора в организации подключите Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) в окне Windows PowerShell.

2. Чтобы создать deP, используйте командлет New-DataEncryptionPolicy, введя следующую команду.

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   Где:

   - *PolicyName* — это имя, которое необходимо использовать для политики. Имена не могут содержать пробелы. Например, USA_mailboxes.

   - *Описание политики* — это удобное описание политики, которое поможет вам вспомнить, для чего нужна политика. В описании можно включить пробелы. Например, "Корневой ключ для почтовых ящиков в США и на ее территориях".

   - *KeyVaultURI1* — это URI для первого ключа в политике. Например, <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>.

   - *KeyVaultURI2* — это URI для второго ключа в политике. Например, <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>. Разделять два URL-адреса на запятую и пробел.

   Пример:
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault02.vault.azure.net/keys/USA_key_01, https://contoso_CentralUSvault02.vault.azure.net/keys/USA_Key_02
   ```

Подробные сведения о синтаксисах и параметрах см. [в обзоре New-DataEncryptionPolicy.](/powershell/module/exchange/new-data-encryptionpolicy)

### <a name="assign-a-dep-to-a-mailbox"></a>Назначение deP почтовому ящику

Назначение deP почтовому ящику с помощью Set-Mailbox. После назначения политики Microsoft 365 шифровать почтовый ящик ключом, идентифицированным в deP.
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

Где *MailboxIdParameter* указывает почтовый ящик пользователя. Дополнительные сведения о Set-Mailbox см. в [списке Set-Mailbox.](/powershell/module/exchange/set-mailbox)

В гибридных средах можно назначить deP данным локального почтового ящика, синхронизированным в Exchange Online клиента. Чтобы назначить deP этим синхронизированным данным почтовых ящиков, вы будете использовать Set-MailUser. Дополнительные сведения о данных почтовых ящиков в гибридной среде см. в локальном почтовом ящике с Outlook для iOS и Android с гибридной современной проверкой [подлинности.](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

Где *MailUserIdParameter* указывает пользователя почты (также известного как пользователь с включенной почтой). Дополнительные сведения о Set-MailUser см. в [списке Set-MailUser.](/powershell/module/exchange/set-mailuser)

## <a name="create-a-dep-for-use-with-sharepoint-online-onedrive-for-business-and-teams-files"></a>Создание deP для использования с SharePoint Online, OneDrive для бизнеса и Teams файлами

Перед началом работы убедитесь, что вы выполнили задачи, необходимые для набора хранилища ключей Azure. Сведения см. в [перенастройка клиентского ключа](customer-key-set-up.md).
  
Чтобы настроить клиентский ключ для SharePoint Online, OneDrive для бизнеса и Teams, выполните эти действия, удаленно подключившись к SharePoint Online с помощью Windows PowerShell.
  
Вы связываете deP с набором ключей, хранимых в хранилище ключей Azure. Для всех данных в одном географическом расположении, называемом также гео, применяется deP. Если вы используете функцию multi-geo Office 365, можно создать один DEP на один гео с возможностью использования различных ключей для каждого гео. Если вы не используете multi-geo, вы можете создать один DEP в вашей организации для использования с SharePoint Online, OneDrive для бизнеса и Teams файлами. Microsoft 365 для шифрования данных в этом географе используются ключи, выявленные в deP. Чтобы создать DEP, вам нужны URL-адреса key Vault, полученные во время установки. Сведения см. в [элементе Получение URI для каждого ключа Azure Key Vault.](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)
  
Помните! При создании DEP укажите два ключа в двух разных хранилищах ключей Azure. Создайте эти клавиши в двух отдельных регионах Azure для обеспечения избыточности геоизбытки.
  
Чтобы создать deP, необходимо удаленно подключиться к SharePoint Online с помощью Windows PowerShell.
  
1. На локальном компьютере с помощью учетной записи работы или школы, которая имеет глобальные разрешения администратора в организации, Подключение SharePoint [Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps).

2. В Microsoft Office SharePoint Online управленческой оболочки выполните Register-SPODataEncryptionPolicy следующим образом:

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <adminSiteCollectionURL> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   Пример:
  
   ```powershell
   Register-SPODataEncryptionPolicy -Identity https://contoso.sharepoint.com -PrimaryKeyVaultName 'stageRG3vault' -PrimaryKeyName 'SPKey3' -PrimaryKeyVersion 'f635a23bd4a44b9996ff6aadd88d42ba' -SecondaryKeyVaultName 'stageRG5vault' -SecondaryKeyName 'SPKey5' -SecondaryKeyVersion '2b3e8f1d754f438dacdec1f0945f251a’
   ```

   При регистрации deP шифрование начинается с данных в гео. Шифрование может занять некоторое время. Дополнительные сведения об использовании этого параметра см. в [сайте Register-SPODataEncryptionPolicy.](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps)

### <a name="view-the-deps-youve-created-for-exchange-online-mailboxes"></a>Просмотр dePs, созданных для Exchange Online почтовых ящиков

Чтобы просмотреть список всех созданных для почтовых ящиков dePs, используйте Get-DataEncryptionPolicy PowerShell.

1. С помощью учетной записи работы или школы, которая имеет глобальные разрешения администратора в вашей организации, подключите Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Чтобы вернуть все dePs в организации, запустите Get-DataEncryptionPolicy без параметров.

   ```powershell
   Get-DataEncryptionPolicy
   ```

   Дополнительные сведения о Get-DataEncryptionPolicy см. в этой записи [в get-DataEncryptionPolicy.](/powershell/module/exchange/get-dataencryptionpolicy)

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a>Назначение deP перед переносом почтового ящика в облако

При назначении deP Microsoft 365 шифрует содержимое почтового ящика с помощью назначенного deP во время миграции. Этот процесс более эффективен, чем перенос почтового ящика, назначение deP и ожидание шифрования, которое может занять несколько часов или, возможно, дней.

Чтобы назначить deP почтовому ящику перед переносом Office 365, запустите Set-MailUser в Exchange Online PowerShell:

1. С помощью учетной записи работы или школы, которая имеет глобальные разрешения администратора в вашей организации, подключите Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Запустите Set-MailUser.

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   Если *GeneralMailboxOrMailUserIdParameter* указывает почтовый ящик, а *DataEncryptionPolicyIdParameter* — это ID deP. Дополнительные сведения о Set-MailUser см. в [списке Set-MailUser.](/powershell/module/exchange/set-mailuser)

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>Определение deP, назначенного почтовому ящику

Чтобы определить deP, назначенное почтовому ящику, используйте Get-MailboxStatistics. В этом кодлете возвращается уникальный идентификатор (GUID).
  
1. С помощью учетной записи работы или школы, которая имеет глобальные разрешения администратора в вашей организации, подключите Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   Если *GeneralMailboxOrMailUserIdParameter* указывает почтовый ящик, а DataEncryptionPolicyID возвращает GUID deP. Дополнительные сведения о Get-MailboxStatistics см. в [списке Get-MailboxStatistics.](/powershell/module/exchange/get-mailboxstatistics)
  
2. Запустите Get-DataEncryptionPolicy, чтобы узнать удобное имя deP, которому назначен почтовый ящик.
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   Если *GUID* — это GUID, возвращаемая Get-MailboxStatistics на предыдущем этапе.

## <a name="verify-that-customer-key-has-finished-encryption"></a>Убедитесь, что ключ клиента завершил шифрование

Вне зависимости от того, были ли вы свернут ключ клиента, назначен новый deP или перенесен почтовый ящик, используйте действия в этом разделе для обеспечения завершения шифрования.

### <a name="verify-encryption-completes-for-exchange-online-mailboxes"></a>Проверка завершения шифрования для Exchange Online почтовых ящиков

Шифрование почтового ящика может занять некоторое время. При первом шифровании почтовый ящик должен полностью перемещаться из одной базы данных в другую, прежде чем служба сможет шифровать почтовый ящик.
  
Используйте Get-MailboxStatistics, чтобы определить, зашифрован ли почтовый ящик.
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

Свойство IsEncrypted возвращает значение  true, если почтовый ящик зашифрован, и значение **false,** если почтовый ящик не зашифрован. Время выполнения ходов почтовых ящиков зависит от количества почтовых ящиков, которым вы назначаете deP впервые, и размера почтовых ящиков. Если почтовые ящики не были зашифрованы через неделю с того времени, как вы назначены deP, обратитесь в Корпорацию Майкрософт.

Этот New-MoveRequest больше не доступен для перемещения локальных почтовых ящиков. Дополнительные [сведения можно найти в](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) этом объявлении.

### <a name="verify-encryption-completes-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Проверка завершения шифрования для SharePoint, OneDrive для бизнеса и Teams файлов

Проверьте состояние шифрования, запуская Get-SPODataEncryptionPolicy следующим образом:

```PowerShell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

Выход из этого комлета включает в себя:
  
- URI основного ключа.

- URI вторичного ключа.

- Состояние шифрования для гео. Возможные состояния:

  - **Незарегистрированные:** Шифрование ключа клиента еще не применено.

  - **Регистрация:** Шифрование ключа клиента было применено, и ваши файлы находятся в процессе шифрования. Если ключ для георегистра регистрируется, вам также будет показана информация о том, какой процент сайтов в геополии завершен, чтобы можно было отслеживать ход шифрования.

  - **Зарегистрированы:** Было применено шифрование ключа клиента, и все файлы на всех сайтах были зашифрованы.

  - **Прокатка:** В настоящее время продолжается перекат ключей. Если ключ для геоската катится, вам также будет показана информация о том, какой процент сайтов завершил операцию рулона ключа, чтобы можно было отслеживать ход выполнения.

## <a name="get-details-about-deps-you-use-with-multiple-workloads"></a>Сведения об использовании dePs с несколькими рабочими нагрузками

Чтобы получить сведения обо всех созданных для использования dePs с несколькими рабочими нагрузками, выполните следующие действия:

1. На локальном компьютере с помощью учетной записи работы или учебного заведения с разрешениями администратора глобального администратора или администратора соответствия требованиям подключайтесь к Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) в Windows PowerShell окне.

   - Чтобы вернуть список всех многопрофильных dePs в организации, запустите эту команду.

     ```powershell
        Get-M365DataAtRestEncryptionPolicy
     ```

   - Чтобы вернуть сведения о конкретном deP, запустите эту команду. В этом примере возвращается подробная информация для deP с именем "Contoso_Global".

     ```powershell
        Get-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global"
     ```

## <a name="get-multi-workload-dep-assignment-information"></a>Получить сведения о назначении deP с несколькими рабочими нагрузками

Чтобы узнать, какой deP в настоящее время назначен вашему клиенту, выполните следующие действия. 

1. На локальном компьютере с помощью учетной записи работы или учебного заведения с разрешениями администратора глобального администратора или администратора соответствия требованиям подключайтесь к Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) в Windows PowerShell окне.

2. Введите эту команду.

   ```powershell
      Get-M365DataAtRestEncryptionPolicyAssignment
   ```

## <a name="disable-a-multi-workload-dep"></a>Отключение deP с несколькими рабочими нагрузками

Прежде чем отключить deP с несколькими рабочими нагрузками, отключите deP от рабочих нагрузок в клиенте. Чтобы отключить deP, используемый с несколькими рабочими нагрузками, выполните следующие действия:

1. На локальном компьютере с помощью учетной записи работы или учебного заведения с разрешениями администратора глобального администратора или администратора соответствия требованиям подключайтесь к Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) в Windows PowerShell окне.

2. Запустите Set-M365DataAtRestEncryptionPolicy.
  
   ```powershell
   Set-M365DataAtRestEncryptionPolicy -[Identity] "PolicyName" -Enabled $false
   ```

Где *PolicyName* — это имя или уникальный ID политики. Например, Contoso_Global.

Пример:

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global" -Enabled $false
```

## <a name="restore-azure-key-vault-keys"></a>Восстановление ключей Azure Key Vault

Перед выполнением восстановления используйте возможности восстановления, предоставляемые мягким удалением. Для всех ключей, используемых с ключом клиента, требуется включить мягкое удаление. Мягкое удаление действует как корзина для переработки и позволяет восстанавливать до 90 дней без необходимости восстановления. Восстановление должно требоваться только в экстремальных или необычных обстоятельствах, например, если ключ или хранилище ключа потеряно. Если необходимо восстановить ключ для использования с ключом клиента, в Azure PowerShell выполните Restore-AzureKeyVaultKey следующим образом:
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

Например:
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

Если хранилище ключей уже содержит ключ с тем же именем, операция восстановления сбой. Restore-AzKeyVaultKey восстанавливает все ключевые версии и все метаданные для ключа, включая имя ключа.
  
## <a name="manage-key-vault-permissions"></a>Управление разрешениями хранилища ключей

Доступно несколько cmdlets, которые позволяют просматривать и при необходимости удалять разрешения на хранилище ключей. Может потребоваться удалить разрешения, например, когда сотрудник покидает команду. Для каждой из этих задач вы будете использовать Azure PowerShell. Сведения о Azure PowerShell см. в [обзоре Azure PowerShell.](/powershell/azure/)

Чтобы просмотреть разрешения хранилища ключей, запустите Get-AzKeyVault.

```powershell
Get-AzKeyVault -VaultName <vault name>
```

Например:

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

Чтобы удалить разрешения администратора, запустите Remove-AzKeyVaultAccessPolicy:
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

Например:

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="roll-back-from-customer-key-to-microsoft-managed-keys"></a>Откат от ключа клиента к управляемым клавишам Майкрософт

Если вам нужно вернуться к клавишам с управлением Майкрософт, вы можете. При отключении данные повторно шифруются с помощью шифрования по умолчанию, поддерживаемого каждой отдельной рабочей нагрузкой. Например, Exchange Online шифрование по умолчанию с помощью управляемых Microsoft ключей.

> [!IMPORTANT]
> Offboarding — это не то же самое, что очистка данных. Очистка данных навсегда удаляет данные вашей организации из Microsoft 365, offboarding этого не делает. Вы не можете выполнить очистку данных для нескольких политик рабочей нагрузки.

Если вы решите больше не использовать клиентский ключ для назначения депов с несколькими рабочими нагрузками, вам потребуется связаться с поддержкой Майкрософт с запросом на "отключение" от ключа клиента. Попросите команду поддержки подать запрос на службу Microsoft 365 клиента. Связаться с m365-ck@service.microsoft.com, если у вас есть какие-либо вопросы.

Если вы больше не хотите шифровать отдельные почтовые ящики с помощью dePs уровня почтовых ящиков, можно отогнать dePs уровня почтовых ящиков из всех почтовых ящиков.

Чтобы отогнать dePs почтового ящика, используйте Set-Mailbox PowerShell.

1. С помощью учетной записи работы или школы, которая имеет глобальные разрешения администратора в вашей организации, подключите Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Запустите Set-Mailbox.

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

При запуске этого cmdlet открепит назначенное в настоящее время deP и повторно зашифровка почтового ящика с помощью DEP, связанного с ключами microsoft-managed по умолчанию. Нельзя отоименить deP, используемый управляемыми ключами Майкрософт. Если вы не хотите использовать ключи с управлением Майкрософт, вы можете назначить в почтовый ящик другой DEP ключа клиента.

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a>Отзовите ключи и запустите процесс очистки данных

Вы контролируете отзыв всех корневых ключей, включая ключ доступности. Ключ клиента обеспечивает контроль за аспектом планирования выхода из системы нормативных требований для вас. Если вы решите отопустить ключи для очистки данных и выхода из службы, служба удаляет ключ доступности после завершения процесса очистки данных. Это поддерживается для dePs ключа клиента, которые назначены отдельным почтовым ящикам.

Microsoft 365 аудит и проверяет путь очистки данных. Дополнительные сведения см. в отчете SSAE 18 SOC 2, доступном на [портале доверия к службам.](https://servicetrust.microsoft.com/) Кроме того, Корпорация Майкрософт рекомендует следующие документы:

- [Руководство по оценке рисков и обеспечению соответствия требованиям для финансовых учреждений в Облаке Майкрософт](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [Соображения планирования выхода O365](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

Purging of multi-workload DEP is not supported for Microsoft 365 Customer Key. DeP с несколькими рабочими нагрузками используется для шифрования данных между несколькими рабочими нагрузками для всех пользователей-клиентов. Чистка таких deP приведет к недоступности данных из нескольких рабочих нагрузок. Если вы решите полностью Microsoft 365 службы, можно продолжить путь удаления клиента в документированном процессе. Узнайте, [как удалить клиента в Azure Active Directoy.](/azure/active-directory/enterprise-users/directory-delete-howto)

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a>Отзовите ключи клиента и ключ доступности для Exchange Online и Skype для бизнеса

Когда вы инициируете путь очистки данных для Exchange Online и Skype для бизнеса, вы установите постоянный запрос очистки данных на deP. Это навсегда удаляет зашифрованные данные в почтовых ящиках, которым назначен этот deP.

Так как вы можете запускать только комдлет PowerShell по одному deP одновременно, перед началом пути очистки данных рассмотрите возможность повторного перенанаружания единого deP для всех почтовых ящиков.

> [!WARNING]
> Не используйте путь очистки данных для удаления подмножество почтовых ящиков. Этот процесс предназначен только для клиентов, которые выходят из службы.

Чтобы инициировать путь очистки данных, выполните следующие действия:

1. Удалите разрешения на обертывание и открутку для "O365 Exchange Online" из хранилища ключей Azure.

2. С помощью учетной записи для работы или школы, которая имеет глобальные права администратора в организации, подключите Exchange Online [PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

3. Для каждого deP, который содержит почтовые ящики, которые необходимо удалить, выполните [набор-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) следующим образом.

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   Если команда сбой, убедитесь, что вы удалили Exchange Online с обоих ключей в Хранилище ключей Azure, как указано ранее в этой задаче.После того как вы установите переключатель PermanentDataPurgeRequested с помощью Set-DataEncryptionPolicy, вы больше не сможете назначить этот deP почтовым ящикам.

4. Обратитесь в службу поддержки Корпорации Майкрософт и запросите eDocument очистки данных.

    По вашему запросу Корпорация Майкрософт отправляет вам юридический документ для подтверждения и авторизации удаления данных. Человек в вашей организации, который зарегистрировался в качестве утвержденного в предложении FastTrack во время входной регистрации, должен подписать этот документ. Как правило, это руководитель или другое назначенное лицо в вашей компании, которому по закону разрешено подписывать документы от имени вашей организации.

5. После того как ваш представитель подписал юридический документ, верни его в Корпорацию Майкрософт (как правило, с помощью подписи eDoc).

    Когда Корпорация Майкрософт получает юридический документ, Корпорация Майкрософт запускает комлеты, чтобы вызвать очистку данных, которая сначала удаляет политику, отмечает почтовые ящики для постоянного удаления, а затем удаляет ключ доступности. После завершения процесса очистки данных данные будут очищены, недоступны для Exchange Online и не могут быть восстановлены.

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Отзовите ключи клиента и ключ доступности для SharePoint, OneDrive для бизнеса и Teams файлов

Чтобы инициировать путь очистки данных для SharePoint Online, OneDrive для бизнеса и Teams, выполните следующие действия:

1. Отзови доступ к хранилищем ключей Azure. Все администраторы хранилища ключей должны согласиться на отвод доступа.

   Хранилище ключей Azure для SharePoint Online не удаляется. Хранилища ключей могут быть общими для нескольких SharePoint и dePs.

2. Свяжитесь с Корпорацией Майкрософт, чтобы удалить ключ доступности.

    Когда вы обратитесь в Корпорацию Майкрософт, чтобы удалить ключ доступности, мы отправим вам юридический документ. Человек в вашей организации, который зарегистрировался в качестве утвержденного в предложении FastTrack во время входной регистрации, должен подписать этот документ. Как правило, это руководитель или другой назначенный человек в вашей компании, который имеет юридические права подписывать документы от имени организации.

3. Как только ваш представитель подпишет юридический документ, верни его в Microsoft (обычно с помощью подписи eDoc).

   Когда Корпорация Майкрософт получает юридический документ, мы запускаем комлеты, чтобы вызвать очистку данных, которая выполняет крипто-удаление ключа клиента, ключа сайта и всех отдельных ключей каждого документа, безвозвратно нарушая иерархию ключей. После завершения очистки данных данные будут очищены.

## <a name="related-articles"></a>Связанные статьи

- [Шифрование службы с помощью ключа клиента](customer-key-overview.md)

- [Узнайте о ключе доступности](customer-key-availability-key-understand.md)

- [Настройка ключа клиента](customer-key-set-up.md)

- [Смена или ротация ключа клиента или ключа доступности](customer-key-availability-key-roll.md)

- [Защищенное хранилище пользователя](customer-lockbox-requests.md)

- [Шифрование служб](office-365-service-encryption.md)