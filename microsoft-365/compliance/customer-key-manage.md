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
ms.openlocfilehash: dbdbd61b4d06e183d8cc5461122e316b2b6b1797
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352206"
---
# <a name="manage-customer-key"></a>Управление ключом клиента

После того как вы настроили ключ клиента для Office 365, вы можете управлять ключами, как описано в этой статье. Дополнительные сведения о ключе клиента см.

## <a name="restore-azure-key-vault-keys"></a>Восстановление ключей Azure Key Vault

Перед выполнением восстановления используйте возможности восстановления, предоставляемые функцией обратимого удаления. Для всех ключей, используемых с ключом клиента, необходимо включить функцию обратимого удаления. Обратимое удаление действует как корзина и позволяет выполнить восстановление до 90 дней без необходимости восстановления. Восстановление должно требоваться только в крайних или необычных обстоятельствах, например, при потере ключа или основного хранилища ключей. Если необходимо восстановить ключ для использования с ключом клиента, в Azure PowerShell запустите командлет Restore – Азурекэйваулткэй следующим образом:
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

Например:
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

Если хранилище ключей уже содержит ключ с таким же именем, операция восстановления завершается с ошибкой. Restore — Азкэйваулткэй восстанавливает все ключевые версии и все метаданные для ключа, включая имя ключа.
  
## <a name="manage-key-vault-permissions"></a>Управление разрешениями для хранилища ключей

Доступно несколько командлетов, которые позволяют просматривать и при необходимости удалять разрешения для хранилища ключей. Возможно, вам потребуется удалить разрешения, например, когда сотрудник покидает команду. Для каждой из этих задач вы будете использовать Azure PowerShell. Сведения о Azure PowerShell можно найти в статье [Обзор Azure PowerShell](https://docs.microsoft.com/powershell/azure/).

Чтобы просмотреть разрешения на доступ к хранилищу ключей, запустите командлет Get – Азкэйваулт.

```powershell
Get-AzKeyVault -VaultName <vault name>
```

Например:

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

Чтобы удалить разрешения администратора, запустите командлет Remove – Азкэйваултакцессполици:
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

Например:

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="manage-data-encryption-policies-deps-with-customer-key"></a>Управление политиками шифрования данных (ДЕПС) с помощью ключа клиента

Ключевые обработчики клиентов ДЕПС отличаются в разных службах. Например, вы можете создать другое количество ДЕПС для разных служб.

**Exchange Online и Skype для бизнеса:** Можно создать до 50 ДЕПС. Инструкции приведены в разделе [Создание политики шифрования данных (DEP) для использования с Exchange Online и Skype для бизнеса](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business).

**Файлы SharePoint Online, OneDrive для бизнеса и teams:** Функция DEP применяется к данным в одном географическом расположении, также называемом _географическим_. Если вы используете функцию поддержки нескольких регионов в Office 365, вы можете создать одну функцию DEP для каждого географического объекта. Если вы не используете поддержку нескольких регионов, вы можете создать одну функцию DEP. Как правило, функция DEP создается при настройке ключа клиента. Инструкции, приведенные в разделе [Создание политики шифрования данных (DEP) для каждого географического региона SharePoint Online и OneDrive для бизнеса](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo).

### <a name="view-the-deps-youve-created-for-exchange-online-and-skype-for-business"></a>Просмотр созданного ДЕПС для Exchange Online и Skype для бизнеса

Чтобы просмотреть список всех ДЕПС, созданных для Exchange Online и Skype для бизнеса с помощью командлета Get-Dataencryptionpolicy используется PowerShell, выполните указанные ниже действия.

1. С помощью рабочей или учебной учетной записи, имеющей разрешения глобального администратора в Организации, [подключитесь к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).

2. Чтобы возвратить все ДЕПС в Организации, выполните командлет Get – Dataencryptionpolicy используется без параметров.

  ```powershell
  Get-DataEncryptionPolicy
  ```

  Дополнительные сведения о командлете Get – Dataencryptionpolicy используется можно найти в статье [Get – dataencryptionpolicy используется](https://docs.microsoft.com/powershell/module/exchange/get-dataencryptionpolicy?view=exchange-ps).

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a>Назначение функции DEP перед переносом почтового ящика в облако

При назначении функции DEP Microsoft 365 шифрует содержимое почтового ящика с помощью назначенной функции DEP во время миграции. Этот процесс является более эффективным, чем перенос почтового ящика, назначение DEP, а затем ожидание выполнения шифрования, что может занять несколько часов или, возможно, дней.

Чтобы назначить средство предотвращения выполнения данных для почтового ящика перед его переносом в Office 365, выполните командлет Set-MailUser в Exchange Online PowerShell:

1. С помощью рабочей или учебной учетной записи, имеющей разрешения глобального администратора в Организации, [подключитесь к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).

2. Выполните командлет Set – MailUser.

  ```powershell
  Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
  ```

  Где *женералмаилбоксормаилусеридпараметер* указывает почтовый ящик, а *датаенкриптионполициидпараметер* — идентификатор функции DEP. Дополнительные сведения о командлете Set – MailUser см. в разделе [Set – MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser?view=exchange-ps).

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>Определение функции DEP, назначенной для почтового ящика

Чтобы определить, какая функция DEP назначена почтовому ящику, используйте командлет Get – MailboxStatistics. Командлет возвращает уникальный идентификатор (GUID).
  
1. С помощью рабочей или учебной учетной записи, имеющей разрешения глобального администратора в Организации, [подключитесь к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   Где *женералмаилбоксормаилусеридпараметер* указывает почтовый ящик, а ДАТАЕНКРИПТИОНПОЛИЦИИД Возвращает GUID объекта DEP. Дополнительные сведения о командлете Get – MailboxStatistics можно найти в статье [Get – MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics?view=exchange-ps).
  
2. Выполните командлет Get-Dataencryptionpolicy используется, чтобы узнать понятное имя DEP, которому назначен почтовый ящик.
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   Где *GUID* — это идентификатор GUID, возвращенный командлетом Get-MailboxStatistics на предыдущем шаге.

## <a name="verify-that-customer-key-has-finished-encryption"></a>Проверка того, что ключ клиента завершил шифрование

После того как вы выполнили откат ключа клиента, назначили новую функцию DEP или перенесли почтовый ящик, выполните действия, описанные в этом разделе, чтобы убедиться, что шифрование завершено.

### <a name="verify-encryption-completes-for-exchange-online-and-skype-for-business"></a>Проверка того, что шифрование завершено для Exchange Online и Skype для бизнеса

Шифрование почтового ящика может занять некоторое время. Рекомендуется подождать 72 часов, прежде чем пытаться проверить шифрование после изменения функции DEP или при первом назначении функции защиты почтового ящика.
  
Используйте командлет Get-MailboxStatistics, чтобы определить, зашифрован ли почтовый ящик.
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

Свойство IsFalse возвращает значение **true** , если почтовый ящик зашифрован, и значение **false** , если почтовый ящик не зашифрован.

Время на завершение перемещения почтовых ящиков зависит от размера почтового ящика. Если ключ клиента не полностью зашифровал почтовый ящик после 72 часов с момента назначения новой функции DEP, инициируйте перемещение почтового ящика. Для этого используйте командлет New – MoveRequest и укажите псевдоним почтового ящика. Например:
  
```powershell
New-MoveRequest <alias>
```

Для получения дополнительных сведений об этом командлете обратитесь к разделу [Get – MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/new-moverequest?view=exchange-ps).

### <a name="verify-encryption-completes-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>Проверка того, что шифрование выполнено для SharePoint Online, OneDrive для бизнеса и файлов Teams

Проверьте состояние шифрования, выполнив командлет Get – Сподатаенкриптионполици, как показано ниже.

```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

Выходные данные этого командлета включают:
  
- Универсальный код ресурса (URI) первичного ключа.

- Универсальный код ресурса (URI) вторичного ключа.

- Состояние шифрования для Geo. Возможные состояния:

  - **Регистрация незарегистрирована:** Шифрование ключей клиентов еще не применено.

  - **Регистрация:** Шифрование ключей клиентов применено, а файлы находятся в процессе шифрования. Если ключ для географического проекта регистрируется, вы также увидите сведения о том, какой процент сайтов в гео завершен, чтобы можно было отслеживать ход шифрования.

  - **Зарегистрировано:** Шифрование ключей клиентов применено, а все файлы на всех сайтах зашифрованы.

  - **Пошаговое руководство:** Выполняется основной этап. Если ключ для Geo является скользящим, вы также увидите сведения о том, на каком проценте сайтов выполнялась операция полного выполнения, чтобы можно было отслеживать ход выполнения.

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a>Отзыв ключей и начало процесса очистки данных

Вы управляете отзывами всех корневых ключей, включая ключ доступности. Ключ клиента обеспечивает управление аспектом планирования выхода нормативных требований. Если вы решили отозвать ключи для очистки данных и выйти из службы, служба удаляет ключ доступности после завершения процесса очистки данных.

Microsoft 365 выполняет аудит и проверку пути очистки данных. Для получения дополнительных сведений посетите отчет ССАЕ 18 SOC 2, доступный на [портале доверия службы](https://servicetrust.microsoft.com/). Кроме того, корпорация Майкрософт рекомендует следующие документы:

- [Оценка риска и рекомендации по соответствию финансовых учреждениям в облаке Майкрософт](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [Рекомендации по планированию выхода O365](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

Путь очистки данных слегка различается для разных служб.

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a>Отзыв ключей клиентов и ключа доступности для Exchange Online и Skype для бизнеса

Когда вы инициируете путь очистки данных для Exchange Online и Skype для бизнеса, вы настраиваете постоянный запрос на очистку данных для функции DEP. Это приведет к удалению зашифрованных данных в почтовых ящиках, к которым назначена функция DEP.

Так как командлет PowerShell можно запускать только с одним компонентом DEP, рекомендуется переназначить одну функцию DEP для всех почтовых ящиков, прежде чем инициировать путь очистки данных.

> [!WARNING]
> Не используйте путь очистки данных для удаления подмножества почтовых ящиков. Этот процесс предназначен только для клиентов, использующих службу.

Чтобы инициировать путь очистки данных, выполните указанные ниже действия.

1. Удалите разрешения для переноса и переноса для "O365 Exchange Online" из Azure Key Vault.

2. С помощью рабочей или учебной учетной записи, имеющей права глобального администратора в Организации, [подключитесь к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).

3. Для каждого компонента DEP, содержащего почтовые ящики, которые необходимо удалить, выполните командлет [Set – dataencryptionpolicy используется](https://docs.microsoft.com/powershell/module/exchange/set-dataencryptionpolicy) следующим образом.

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   Если команда не выполняется, убедитесь, что вы удалили разрешения Exchange Online из обоих ключей в Azure Key Vault, как указано ранее в этой задаче.После установки переключателя параметрами permanentdatapurgerequested с помощью командлета Set – Dataencryptionpolicy используется вы больше не сможете назначать эту функцию DEP для почтовых ящиков.

4. Обратитесь в службу поддержки Майкрософт и запросите Едокумент очистки данных.

    По Вашему запросу корпорация Майкрософт отправляет вам юридический документ для подтверждения и авторизации удаления данных. Этот документ должен быть подписан сотрудником вашей организации, который зарегистрировался в качестве утверждающего в FastTrack. Обычно это руководитель или другой назначенный сотрудник компании, который уполномоченным пользователям подписывать документы от имени вашей организации.

5. После того как ваш представитель подписал юридический документ, верните его в корпорацию Майкрософт (обычно через подпись едок).

    Когда корпорация Майкрософт получает юридический документ, корпорация Майкрософт запускает командлеты для запуска очистки данных, которая сначала удаляет политику, помечает почтовые ящики для постоянных удалений, а затем удаляет ключ доступности. После завершения процесса очистки данных данные очищаются, недоступны для Exchange Online и не могут быть восстановлены.

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>Отзыв ключей клиентов и ключа доступности для файлов SharePoint Online, OneDrive для бизнеса и Teams

Чтобы инициировать путь очистки данных для SharePoint Online, OneDrive для бизнеса и файлов Teams, выполните указанные ниже действия.

1. Отзыв доступа к Azure Key Vault. Все администраторы основного хранилища должны согласиться на отзыв доступа.

   Вы не удаляете Azure Key Vault для SharePoint Online. Основные хранилища могут быть общими для нескольких клиентов SharePoint Online и ДЕПС.

2. Обратитесь в корпорацию Майкрософт, чтобы удалить ключ доступности.

    Когда вы обратитесь в корпорацию Майкрософт, чтобы удалить ключ доступности, мы отправим вам юридический документ. Этот документ должен быть подписан сотрудником вашей организации, который зарегистрировался в качестве утверждающего в FastTrack. Как правило, это руководитель или другой сотрудник компании, уполномоченный подписывать документы от имени вашей организации.

3. Когда ваш представитель подписывает юридический документ, верните его в корпорацию Майкрософт (обычно через подпись едок).

   Когда корпорация Майкрософт получает юридический документ, мы выполняем командлеты для запуска очистки данных, которая выполняет удаление шифрования ключа клиента, ключа сайта и всех отдельных ключей документа, ирревокабли нарушая иерархию ключей. После завершения командлетов по очистке данных данные очищаются.

## <a name="related-articles"></a>Статьи по теме

- [Шифрование службы с помощью ключа клиента](customer-key-overview.md)

- [Сведения о ключе доступности](customer-key-availability-key-understand.md)

- [Настройка ключа клиента](customer-key-set-up.md)

- [Смена или ротация ключа клиента или ключа доступности](customer-key-availability-key-roll.md)

- [Защищенное хранилище пользователя](customer-lockbox-requests.md)

- [Шифрование службы](office-365-service-encryption.md)
