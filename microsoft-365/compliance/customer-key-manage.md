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
# <a name="manage-customer-key"></a>Управление ключом клиента

После того как вы настроите ключ клиента для Office 365, вы сможете управлять ключами, как описано в этой статье. Узнайте больше о ключе клиента в соответствующих темах.

## <a name="restore-azure-key-vault-keys"></a>Восстановление ключей Хранилища ключей Azure

Перед выполнением восстановления используйте возможности восстановления, предоставляемые функцией мягкого удаления. Все ключи, используемые с ключом клиента, должны быть включены для мягкого удаления. Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore. Восстановление необходимо только в крайних или необычных обстоятельствах, например, если ключ или хранилище ключей потеряно. Если необходимо восстановить ключ для использования с ключом клиента, в Azure PowerShell выполните Restore-AzureKeyVaultKey следующим образом:
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

Пример:
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

Если хранилище ключей уже содержит ключ с таким же именем, операция восстановления не будет работать. Restore-AzKeyVaultKey восстановления всех ключевых версий и всех метаданных ключа, включая имя ключа.
  
## <a name="manage-key-vault-permissions"></a>Управление разрешениями хранилища ключей

Доступно несколько cmdlets, которые позволяют просматривать и при необходимости удалять разрешения хранилища ключей. Может потребоваться удалить разрешения, например, когда сотрудник покидает команду. Для каждой из этих задач используется Azure PowerShell. Сведения о Azure Powershell см. в [обзоре Azure PowerShell.](https://docs.microsoft.com/powershell/azure/)

Чтобы просмотреть разрешения хранилища ключей, запустите Get-AzKeyVault управления.

```powershell
Get-AzKeyVault -VaultName <vault name>
```

Пример:

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

Чтобы удалить разрешения администратора, запустите Remove-AzKeyVaultAccessPolicy:
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

Пример:

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="manage-data-encryption-policies-deps-with-customer-key"></a>Управление политиками шифрования данных (DEP) с помощью ключа клиента

Ключ клиента обрабатывает DEP по-разному между различными службами. Например, можно создать разное количество DEP для различных служб.

**Exchange Online и Skype для бизнеса:** Можно создать до 50 DEP. Инструкции см. в инструкциях по созданию политики шифрования данных [(DEP)](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)для использования с Exchange Online и Skype для бизнеса.

**Файлы SharePoint Online, OneDrive для бизнеса и Teams:** DEP применяется к данным в одном географическом расположении, также называемом _географической областью._ Если вы используете функцию Office 365 с несколькими географическими службами, вы можете создать одну DEP для каждого географического. Если вы не используете multi-geo, вы можете создать один DEP. Как правило, deP создается при создании ключа клиента. Инструкции см. в инструкциях по созданию политики шифрования данных [(DEP)](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)для каждого географического центра SharePoint Online и OneDrive для бизнеса.

### <a name="view-the-deps-youve-created-for-exchange-online-and-skype-for-business"></a>Просмотр DEP, созданных для Exchange Online и Skype для бизнеса

Чтобы просмотреть список всех DEP, созданных для Exchange Online и Skype для бизнеса с помощью Get-DataEncryptionPolicy PowerShell, выполните следующие действия.

1. Используя учетную запись для работы или учебного заведения с разрешениями глобального администратора в организации, подключите [к Exchange Online PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

2. Чтобы вернуть все DEP в организации, запустите Get-DataEncryptionPolicy без параметров.

   ```powershell
   Get-DataEncryptionPolicy
   ```

   Дополнительные сведения о Get-DataEncryptionPolicy см. в записи [Get-DataEncryptionPolicy.](https://docs.microsoft.com/powershell/module/exchange/get-dataencryptionpolicy)

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a>Назначение DEP перед переносом почтового ящика в облако

При назначении DEP Microsoft 365 шифрует содержимое почтового ящика с помощью назначенного DEP во время миграции. Этот процесс более эффективен, чем перенос почтового ящика, назначение DEP и ожидание шифрования, которое может занять несколько часов или, возможно, дней.

Чтобы назначить deP почтовому ящику перед его переносом в Office 365, запустите Set-MailUser в Exchange Online PowerShell:

1. Используя учетную запись для работы или учебного заведения с разрешениями глобального администратора в организации, подключите [к Exchange Online PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

2. Запустите Set-MailUser управления.

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   Где *GeneralMailboxOrMailUserIdParameter* указывает почтовый ящик, а *DataEncryptionPolicyIdParameter* — это ИД DEP. Дополнительные сведения о Set-MailUser см. в [сообщении Set-MailUser.](https://docs.microsoft.com/powershell/module/exchange/set-mailuser)

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>Определение DEP, назначенного почтовому ящику

Чтобы определить DEP, назначенное почтовому ящику, используйте Get-MailboxStatistics управления. Он возвращает уникальный идентификатор (GUID).
  
1. Используя учетную запись для работы или учебного заведения с разрешениями глобального администратора в организации, подключите [к Exchange Online PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   Где *GeneralMailboxOrMailUserIdParameter* указывает почтовый ящик, а DataEncryptionPolicyID возвращает GUID DEP. Дополнительные сведения о Get-MailboxStatistics см. в [get-MailboxStatistics.](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics)
  
2. Запустите Get-DataEncryptionPolicy, чтобы узнать имя DEP, которому назначен почтовый ящик.
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   Где *GUID* — это GUID, возвращенный Get-MailboxStatistics на предыдущем шаге.

## <a name="verify-that-customer-key-has-finished-encryption"></a>Проверка того, что шифрование ключа клиента завершено

Выполните действия, которые необходимо выполнить в этом разделе, чтобы убедиться, что шифрование завершено, независимо от того, только что был свернут ключ клиента, назначен новый DEP или перенесен почтовый ящик.

### <a name="verify-encryption-completes-for-exchange-online-and-skype-for-business"></a>Проверка завершения шифрования для Exchange Online и Skype для бизнеса

Шифрование почтового ящика может занять некоторое время. Рекомендуется подождать 72 часа, прежде чем пытаться проверить шифрование после изменения DEP или при первом назначении DEP почтовому ящику.
  
Используйте Get-MailboxStatistics, чтобы определить, зашифрован ли почтовый ящик.
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

Свойство IsEncrypted возвращает значение **true,** если почтовый ящик зашифрован, и значение **false,** если почтовый ящик не зашифрован.

Время завершения перемещения почтового ящика зависит от размера почтового ящика. Если ключ клиента не зашифровыл почтовый ящик полностью через 72 часа после назначения нового DEP, обратитесь за помощью в службу поддержки Майкрософт. Этот New-MoveRequest больше не доступен для локального перемещения почтовых ящиков. Дополнительные [сведения можно найти в этом](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) объявлении.

### <a name="verify-encryption-completes-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>Проверка завершения шифрования файлов SharePoint Online, OneDrive для бизнеса и Teams

Проверьте состояние шифрования, задав Get-SPODataEncryptionPolicy следующим образом:

```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

Выходные данные этого cmdlet включают:
  
- URI первичного ключа.

- URI дополнительного ключа.

- Состояние шифрования для географического положения. Возможные состояния:

  - **Unregistered:** Шифрование ключа клиента еще не применено.

  - **Регистрация:** Шифрование ключа клиента применено, и ваши файлы находятся в процессе шифрования. Если регистрируется ключ для географического объекта, вы также увидите сведения о том, какой процент сайтов в географическом отношении завершен, чтобы можно было отслеживать ход шифрования.

  - **Зарегистрировано:** Шифрование ключа клиента применено, и все файлы на всех сайтах были зашифрованы.

  - **Катящийся:** В настоящее время идет перекат ключа. Если ключ для геооблигации скатился, вы также увидите сведения о том, какой процент сайтов выполнил операцию переката ключей, чтобы можно было отслеживать ход выполнения.

## <a name="unassign-a-dep-from-a-mailbox"></a>Unassign a DEP from a mailbox

Вы отогнание DEP из почтового ящика с помощью параметра Set-mailbox PowerShell и установка `DataEncryptionPolicy` параметра `$NULL` .. При запуске этого cmdlet списываются назначенная в данный момент DEP и повторно шифруется почтовый ящик с помощью DEP, связанного с управляемыми ключами Майкрософт по умолчанию. Вы не можете отоименовать DEP, используемую управляемыми ключами Майкрософт. Если вы не хотите использовать управляемые ключи Майкрософт, вы можете назначить другому DEP почтовому ящику.

Чтобы отоименовать DEP из почтового ящика с помощью Set-Mailbox PowerShell, выполните следующие действия.

1. Используя учетную запись для работы или учебного заведения с разрешениями глобального администратора в организации, подключите [к Exchange Online PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

2. Запустите Set-Mailbox управления.

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a>Отозовите ключи и запустите процесс очистки данных

Вы управляете отзывом всех корневых ключей, включая ключ доступности. Ключ клиента обеспечивает контроль за аспектом планирования выхода нормативных требований. Если вы решите отопустить ключи для очистки данных и выхода из службы, служба удалит ключ доступности после завершения процесса очистки данных.

Microsoft 365 проводит аудит и проверяет путь очистки данных. Дополнительные сведения см. в отчете SSAE 18 SOC 2, доступном на [портале Service Trust Portal.](https://servicetrust.microsoft.com/) Кроме того, корпорация Майкрософт рекомендует следующие документы:

- [Руководство по оценке рисков и обеспечению соответствия требованиям для финансовых учреждений в Microsoft Cloud](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [Вопросы планирования выхода из O365](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

Путь очистки данных немного отличается в разных службах.

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a>Revoke your Customer Keys and the availability key for Exchange Online and Skype for Business

Когда вы инициируете путь очистки данных для Exchange Online и Skype для бизнеса, вы можете настроить постоянный запрос на очистку данных в DEP. Это окончательно удаляет зашифрованные данные в почтовых ящиках, которым назначена deP.

Так как вы можете одновременно запускать только один cmdlet PowerShell для одного DEP, рассмотрите возможность перенамерования одного DEP для всех почтовых ящиков, прежде чем инициировать путь очистки данных.

> [!WARNING]
> Не используйте путь очистки данных для удаления подмножество почтовых ящиков. Этот процесс предназначен только для клиентов, которые выходят из службы.

Чтобы инициировать путь очистки данных, выполните следующие действия:

1. Удалите разрешения на перенос и удаление для "O365 Exchange Online" из хранилищ Ключей Azure.

2. Используя учетную запись для работы или учебного заведения с привилегиями глобального администратора в вашей организации, подключите [к Exchange Online PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

3. Для каждого DEP, содержаного почтовые ящики, [](https://docs.microsoft.com/powershell/module/exchange/set-dataencryptionpolicy) которые требуется удалить, выполните этот запуск следующим образом.

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   Если команда не удалась, убедитесь, что вы удалили разрешения Exchange Online из обоих ключей в Azure Key Vault, как указано ранее в этой задаче.После того как вы настроите переключатель PermanentDataPurgeRequested с помощью Set-DataEncryptionPolicy, вы больше не сможете назначить этот DEP почтовым ящикам.

4. Обратитесь в службу поддержки Майкрософт и запросите очистку данных eDocument.

    По вашему запросу корпорация Майкрософт отправляет вам юридический документ для подтверждения и авторизации удаления данных. Человек в вашей организации, который зарегистрировался в качестве утвержденного в предложении FastTrack во время входной регистрации, должен подписать этот документ. Как правило, это руководитель или другой назначенный человек в вашей компании, который имеет юридические полномочия подписывать документы от имени вашей организации.

5. После того как ваш представитель подписает юридический документ, верните его в корпорацию Майкрософт (обычно с помощью подписи eDoc).

    Когда корпорация Майкрософт получит юридический документ, корпорация Майкрософт запускает для запуска очистки данных, которая сначала удаляет политику, пометит почтовые ящики для постоянного удаления, а затем удалит ключ доступности. После завершения процесса очистки данных данные будут очищены, недоступны для Exchange Online и не будут восстановлены.

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>Отозовите ключи клиента и ключ доступности для файлов SharePoint Online, OneDrive для бизнеса и Teams

Чтобы инициировать путь очистки данных для файлов SharePoint Online, OneDrive для бизнеса и Teams, выполните следующие действия:

1. Отозовет доступ к хранилищу Azure Key Vault. Все администраторы хранилища ключей должны согласиться на отопуск доступа.

   Хранилище Azure Key Vault для SharePoint Online не удаляется. Хранилища ключей могут совместно использовать несколько клиентов SharePoint Online и DEP.

2. Обратитесь в корпорацию Майкрософт, чтобы удалить ключ доступности.

    Когда вы обратитесь в корпорацию Майкрософт, чтобы удалить ключ доступности, мы отправим вам юридический документ. Человек в вашей организации, который зарегистрировался в качестве утвержденного в предложении FastTrack во время входной регистрации, должен подписать этот документ. Как правило, это руководитель или другой назначенный человек в вашей компании, который имеет юридические полномочия подписывать документы от имени вашей организации.

3. После того как ваш представитель подпишет юридический документ, верните его в корпорацию Майкрософт (обычно с помощью подписи eDoc).

   Когда корпорация Майкрософт получит юридический документ, мы запускаем с его запуском очистку данных, которая выполняет криптографической очистку ключа клиента, ключа сайта и всех отдельных ключей для каждого документа, что безвозвратно разрывает иерархию ключей. После завершения работы с данными для очистки данные будут очищены.

## <a name="related-articles"></a>Статьи по теме

- [Шифрование службы с помощью ключа клиента](customer-key-overview.md)

- [Узнайте о ключе доступности](customer-key-availability-key-understand.md)

- [Настройка ключа клиента](customer-key-set-up.md)

- [Смена или ротация ключа клиента или ключа доступности](customer-key-availability-key-roll.md)

- [Защищенное хранилище пользователя](customer-lockbox-requests.md)

- [Шифрование службы](office-365-service-encryption.md)
