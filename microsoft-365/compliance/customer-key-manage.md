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
# <a name="manage-customer-key"></a>Управление ключом клиента

После того как вы настроите ключ клиента для Office 365, вы сможете управлять ключами, как описано в этой статье. Дополнительные данные о ключе клиента в связанных темах.

## <a name="restore-azure-key-vault-keys"></a>Восстановление ключей Azure Key Vault

Перед выполнением восстановления используйте возможности восстановления, предоставляемые мягким удалением. Для всех ключей, используемых с ключом клиента, требуется включить мягкое удаление. Мягкое удаление действует как корзина для переработки и позволяет восстанавливать до 90 дней без необходимости восстановления. Восстановление должно требоваться только в экстремальных или необычных обстоятельствах, например, если ключ или хранилище ключа потеряно. Если необходимо восстановить ключ для использования с ключом клиента, в Azure PowerShell выполните Restore-AzureKeyVaultKey следующим образом:
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

Пример:
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

Если хранилище ключей уже содержит ключ с тем же именем, операция восстановления сбой. Restore-AzKeyVaultKey восстанавливает все ключевые версии и все метаданные для ключа, включая имя ключа.
  
## <a name="manage-key-vault-permissions"></a>Управление разрешениями хранилища ключей

Доступно несколько cmdlets, которые позволяют просматривать и при необходимости удалять разрешения на хранилище ключей. Может потребоваться удалить разрешения, например, когда сотрудник покидает команду. Для каждой из этих задач вы будете использовать Azure PowerShell. Сведения о Azure Powershell см. в [обзоре Azure PowerShell.](/powershell/azure/)

Чтобы просмотреть разрешения хранилища ключей, запустите Get-AzKeyVault.

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

Ключ клиента обрабатывает dePs по-разному между различными службами. Например, можно создать другое число dePs для различных служб.

**Exchange Online и Skype для бизнеса:** Можно создать до 50 dePs. Инструкции см. в [инструкции Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business.](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)

**Файлы SharePoint Online, OneDrive для бизнеса и Teams:** DeP применяется к данным в одном географическом расположении, также называемом _geo_. Если вы используете многофункциональный элемент Office 365, можно создать один DEP на один гео. Если вы не используете multi-geo, можно создать один DEP. Обычно при создании ключа клиента создается deP. Инструкции см. в раздел Создание политики шифрования данных [(DEP)](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)для каждого SharePoint Online и OneDrive для бизнеса geo.

### <a name="view-the-deps-youve-created-for-exchange-online-and-skype-for-business"></a>Просмотр dePs, созданных для Exchange Online и Skype для бизнеса

Чтобы просмотреть список всех dePs, созданных для Exchange Online и Skype для бизнеса с помощью Get-DataEncryptionPolicy PowerShell, выполните эти действия.

1. С помощью учетной записи работы или школы, которая имеет глобальные разрешения администратора в организации, подключите [к Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Чтобы вернуть все dePs в организации, запустите Get-DataEncryptionPolicy без параметров.

   ```powershell
   Get-DataEncryptionPolicy
   ```

   Дополнительные сведения о Get-DataEncryptionPolicy см. в этой записи [в get-DataEncryptionPolicy.](/powershell/module/exchange/get-dataencryptionpolicy)

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a>Назначение deP перед переносом почтового ящика в облако

При назначении deP Microsoft 365 шифрует содержимое почтового ящика с помощью назначенного deP во время миграции. Этот процесс более эффективен, чем перенос почтового ящика, назначение deP и ожидание шифрования, которое может занять несколько часов или, возможно, дней.

Чтобы назначить deP почтовому ящику перед его переносом в Office 365, запустите Set-MailUser в Exchange Online PowerShell:

1. С помощью учетной записи работы или школы, которая имеет глобальные разрешения администратора в организации, подключите [к Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Запустите Set-MailUser.

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   Если *GeneralMailboxOrMailUserIdParameter* указывает почтовый ящик, а *DataEncryptionPolicyIdParameter* — это ID deP. Дополнительные сведения о Set-MailUser см. в [списке Set-MailUser.](/powershell/module/exchange/set-mailuser)

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>Определение deP, назначенного почтовому ящику

Чтобы определить deP, назначенное почтовому ящику, используйте Get-MailboxStatistics. В этом кодлете возвращается уникальный идентификатор (GUID).
  
1. С помощью учетной записи работы или школы, которая имеет глобальные разрешения администратора в организации, подключите [к Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

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

Если только что был свернут ключ клиента, назначен новый deP или перенесен почтовый ящик, используйте действия в этом разделе, чтобы обеспечить завершение шифрования.

### <a name="verify-encryption-completes-for-exchange-online-and-skype-for-business"></a>Проверка завершения шифрования для Exchange Online и Skype для бизнеса

Шифрование почтового ящика может занять некоторое время. Рекомендуется подождать 72 часа, прежде чем попытаться проверить шифрование после изменения deP или при первом назначении deP в почтовый ящик.
  
Используйте Get-MailboxStatistics, чтобы определить, зашифрован ли почтовый ящик.
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

Свойство IsEncrypted возвращает значение  true, если почтовый ящик зашифрован,  а значение false, если почтовый ящик не зашифрован.

Время выполнения ходов почтовых ящиков зависит от размера почтового ящика. Если клиентский ключ не полностью шифрует почтовый ящик через 72 часа после назначения нового deP, обратитесь за помощью в службу поддержки Майкрософт. Этот New-MoveRequest больше не доступен для перемещения локальных почтовых ящиков. Дополнительные [сведения можно найти в](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) этом объявлении.

### <a name="verify-encryption-completes-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Проверка завершения шифрования для файлов SharePoint Online, OneDrive для бизнеса и Teams

Проверьте состояние шифрования, запуская Get-SPODataEncryptionPolicy следующим образом:

```powershell
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

## <a name="unassign-a-dep-from-a-mailbox"></a>Отогнать deP из почтового ящика

Вы отожмести deP из почтового ящика с помощью набора почтовых ящиков PowerShell и установите `DataEncryptionPolicy` параметр `$NULL` . При запуске этого cmdlet ненастоящается назначенное в настоящее время deP и повторное шифрование почтового ящика с помощью DEP, связанного с управляемыми ключами Майкрософт по умолчанию. Нельзя отоименить deP, используемый управляемыми ключами Майкрософт. Если вы не хотите использовать управляемые ключи Майкрософт, вы можете назначить другому deP почтовый ящик.

Чтобы отогнать deP из почтового ящика с помощью Set-Mailbox PowerShell, выполните эти действия.

1. С помощью учетной записи работы или школы, которая имеет глобальные разрешения администратора в организации, подключите [к Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Запустите Set-Mailbox.

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a>Отзовите ключи и запустите процесс очистки данных

Вы контролируете отзыв всех корневых ключей, включая ключ доступности. Ключ клиента обеспечивает контроль за аспектом планирования выхода из системы нормативных требований для вас. Если вы решите отопустить ключи для очистки данных и выхода из службы, служба удаляет ключ доступности после завершения процесса очистки данных.

Microsoft 365 проверяет и проверяет путь очистки данных. Дополнительные сведения см. в отчете SSAE 18 SOC 2, доступном на [портале доверия к службам.](https://servicetrust.microsoft.com/) Кроме того, Корпорация Майкрософт рекомендует следующие документы:

- [Руководство по оценке рисков и обеспечению соответствия требованиям для финансовых учреждений в Облаке Майкрософт](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [Соображения планирования выхода O365](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

Путь очистки данных незначительно различается между различными службами.

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a>Отзовите ключи клиентов и ключ доступности для Exchange Online и Skype для бизнеса

Когда вы инициируете путь очистки данных для Exchange Online и Skype для бизнеса, вы установите постоянный запрос на очистку данных в DEP. Это навсегда удаляет зашифрованные данные в почтовых ящиках, которым назначен этот deP.

Так как вы можете запускать только комдлет PowerShell по одному deP одновременно, перед началом пути очистки данных рассмотрите возможность повторного перенанаружания единого deP для всех почтовых ящиков.

> [!WARNING]
> Не используйте путь очистки данных для удаления подмножество почтовых ящиков. Этот процесс предназначен только для клиентов, которые выходят из службы.

Чтобы инициировать путь очистки данных, выполните следующие действия:

1. Удалите разрешения на обертывание и открутку для "O365 Exchange Online" из хранилища ключей Azure.

2. С помощью учетной записи работы или школы, которая имеет глобальные привилегии администратора в организации, подключите [к Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

3. Для каждого deP, который содержит почтовые ящики, которые необходимо удалить, выполните [набор-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) следующим образом.

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   Если команда не справилась с задачей, убедитесь, что вы удалили разрешения Exchange Online с обоих ключей в хранилище ключей Azure, как указано ранее в этой задаче.После того как вы установите переключатель PermanentDataPurgeRequested с помощью Set-DataEncryptionPolicy, вы больше не сможете назначить этот deP почтовым ящикам.

4. Обратитесь в службу поддержки Корпорации Майкрософт и запросите eDocument очистки данных.

    По вашему запросу Корпорация Майкрософт отправляет вам юридический документ для подтверждения и авторизации удаления данных. Человек в вашей организации, который зарегистрировался в качестве утвержденного в предложении FastTrack во время входной регистрации, должен подписать этот документ. Как правило, это руководитель или другое назначенное лицо в вашей компании, которому по закону разрешено подписывать документы от имени вашей организации.

5. После того как ваш представитель подписал юридический документ, верни его в Корпорацию Майкрософт (как правило, с помощью подписи eDoc).

    Когда Корпорация Майкрософт получает юридический документ, Корпорация Майкрософт запускает комлеты, чтобы вызвать очистку данных, которая сначала удаляет политику, отмечает почтовые ящики для постоянного удаления, а затем удаляет ключ доступности. После завершения процесса очистки данных данные будут очищены, недоступны для Exchange Online и не будут восстановлены.

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Отзовите ключи клиентов и ключ доступности для файлов SharePoint Online, OneDrive для бизнеса и teams

Чтобы инициировать путь очистки данных для файлов SharePoint Online, OneDrive для бизнеса и Teams, выполните следующие действия:

1. Отзови доступ к хранилищем ключей Azure. Все администраторы хранилища ключей должны согласиться на отвод доступа.

   Хранилище ключей Azure для SharePoint Online не удаляется. Хранилища ключей могут быть общими для нескольких клиентов SharePoint Online и dePs.

2. Свяжитесь с Корпорацией Майкрософт, чтобы удалить ключ доступности.

    Когда вы обратитесь в Корпорацию Майкрософт, чтобы удалить ключ доступности, мы отправим вам юридический документ. Человек в вашей организации, который зарегистрировался в качестве утвержденного в предложении FastTrack во время входной регистрации, должен подписать этот документ. Как правило, это руководитель или другой назначенный человек в вашей компании, который имеет юридические права подписывать документы от имени организации.

3. Как только ваш представитель подпишет юридический документ, верни его в Microsoft (обычно с помощью подписи eDoc).

   Когда Корпорация Майкрософт получает юридический документ, мы запускаем комлеты, чтобы вызвать очистку данных, которая выполняет крипто-удаление ключа клиента, ключа сайта и всех отдельных ключей каждого документа, безвозвратно нарушая иерархию ключей. После завершения очистки данных данные будут очищены.

## <a name="related-articles"></a>Статьи по теме

- [Шифрование службы с помощью ключа клиента](customer-key-overview.md)

- [Узнайте о ключе доступности](customer-key-availability-key-understand.md)

- [Настройка ключа клиента](customer-key-set-up.md)

- [Смена или ротация ключа клиента или ключа доступности](customer-key-availability-key-roll.md)

- [Защищенное хранилище пользователя](customer-lockbox-requests.md)

- [Шифрование служб](office-365-service-encryption.md)