---
title: Администрирование почтовых ящиков Exchange Online в среде с поддержкой нескольких регионов
ms.reviewer: adwood
ms.author: chrisda
author: chrisda
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
localization_priority: normal
description: Узнайте, как управлять многоэтабными настройками Exchange Online в среде Microsoft 365 с помощью PowerShell.
ms.openlocfilehash: c8f06318313c4192fc2b3a289727933c5a54f3ad
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905588"
---
# <a name="administering-exchange-online-mailboxes-in-a-multi-geo-environment"></a>Администрирование почтовых ящиков Exchange Online в среде с поддержкой нескольких регионов

Exchange Online PowerShell требуется для просмотра и настройки нескольких свойств гео в среде Microsoft 365. Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

Вам потребуется [модуль Microsoft Azure Active Directory PowerShell](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) версии 1.1.166.0 или более поздней в версии 1.x, чтобы просматривать свойство **PreferredDataLocation** пользовательских объектов. Для пользовательских объектов, синхронизированных с помощью AAD Connect с AAD, нельзя изменить значение **PreferredDataLocation** непосредственно через AAD PowerShell. Через AAD PowerShell можно изменять объекты облачных пользователей. Сведения о подключении к Azure AD PowerShell см. в статье [Подключение к PowerShell](connect-to-microsoft-365-powershell.md).

В многоэтабных средах Exchange Online не нужно делать никаких действий вручную, чтобы добавить geos в клиента. После получения сообщения о том, что multi-geo готова для Exchange Online, все доступные геофайки будут готовы и настроены для использования.

## <a name="connect-directly-to-a-geo-location-using-exchange-online-powershell"></a>Прямое подключение к географическому расположению с помощью Exchange Online PowerShell

Обычно Exchange Online PowerShell подключается к центральному географическому расположению. Но вы также можете подключиться непосредственно к периферийному географическому расположению. В связи с повышением производительности рекомендуется подключаться непосредственно к периферийному географическому расположению, если вы управляете пользователями только в этом расположении.

Требования для установки и использования модуля EXO V2 описаны в статье [Установка и обслуживание модуля EXO V2](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).

Чтобы подключить Exchange Online PowerShell к определенному географическому расположению, параметр *ConnectionUri* отличается от обычных инструкций по подключению. Остальные команды и значения совпадают.

В частности, необходимо добавить значение в `?email=<emailaddress>` конец _значения ConnectionUri._ `<emailaddress>` это адрес электронной почты **любого** почтового ящика в целевом географическом расположении. Ваши разрешения на этот почтовый ящик или отношение к учетным данным не являются фактором; адрес электронной почты просто сообщает Exchange Online PowerShell, где подключиться.

Клиенты Microsoft 365 или Microsoft 365 GCC обычно не должны использовать параметр _ConnectionUri_ для подключения к Exchange Online PowerShell. Но для подключения к определенному географическому расположению необходимо использовать параметр _ConnectionUri,_ чтобы можно было использовать `?email=<emailaddress>` значение.

### <a name="connect-to-a-geo-location-in-exchange-online-powershell"></a>Подключение к геолокации в Exchange Online PowerShell

Следующие инструкции по подключению работают для учетных записей, которые настроены или не настроены для многофакторной проверки подлинности (MFA).

1. В окне Windows PowerShell загрузите модуль EXO V2, выполнив следующую команду:

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. В следующем примере admin@contoso.onmicrosoft.com учетная запись администратора, а целевое географическое расположение — это место, olga@contoso.onmicrosoft.com почтовый ящик.

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName admin@contoso.onmicrosoft.com -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
   ```

3. Введите пароль для admin@contoso.onmicrosoft.com в выявимом запросе. Если учетная запись настроена для MFA, необходимо также ввести код безопасности.

## <a name="view-the-available-geo-locations-that-are-configured-in-your-exchange-online-organization"></a>Просмотр доступных географических расположений, настроенных в организации Exchange Online

Чтобы просмотреть список настроенных географических расположений в Microsoft 365 Multi-Geo, выполните следующую команду в Exchange Online PowerShell:

```powershell
Get-OrganizationConfig | Select -ExpandProperty AllowedMailboxRegions | Format-Table
```

## <a name="view-the-central-geo-location-for-your-exchange-online-organization"></a>Просмотр центрального географического расположения для организации Exchange Online

Чтобы просмотреть центральное географическое расположение клиента, выполните следующую команду в Exchange Online PowerShell:

```powershell
Get-OrganizationConfig | Select DefaultMailboxRegion
```

## <a name="find-the-geo-location-of-a-mailbox"></a>Поиск географического расположения почтового ящика

Командлет **Get-Mailbox** в Exchange Online PowerShell отображает следующие свойства, связанные с поддержкой нескольких регионов, для почтовых ящиков:

- **Database**. Первые 3 буквы имени базы данных соответствуют коду региона, указывающему текущее расположение почтового ящика. Для сетевых архивных почтовых ящиков следует использовать свойство **ArchiveDatabase**.

- **MailboxRegion**. Указывает код географического расположения, установленный администратором (синхронизируется из параметра **PreferredDataLocation** в Azure AD).

- **MailboxRegionLastUpdateTime**. Указывает время последнего обновления MailboxRegion (автоматического или ручного).

Чтобы просмотреть эти свойства для почтового ящика, используйте следующий синтаксис:

```powershell
Get-Mailbox -Identity <MailboxIdentity> | Format-List Database,MailboxRegion*
```

Например, чтобы просмотреть сведения о географическом расположении для почтового ящика chris@contoso.onmicrosoft.com, выполните следующую команду:

```powershell
Get-Mailbox -Identity chris@contoso.onmicrosoft.com | Format-List Database, MailboxRegion*
```

Выходные данные команды выглядят так:

```powershell
Database                    : EURPR03DG077-db007
MailboxRegion               : EUR
MailboxRegionLastUpdateTime : 2/6/2018 8:21:01 PM
```

> [!NOTE]
> Если код геолокации в имени базы данных не соответствует значению **MailboxRegion,** почтовый ящик будет автоматически помещаться в очередь перемещения и перемещен в географическое расположение, указанное значением **MailboxRegion** (Exchange Online ищет несоответствие между этими значениями свойств).

## <a name="move-an-existing-cloud-only-mailbox-to-a-specific-geo-location"></a>Перемещение существующего облачного почтового ящика в определенное географическое расположение

Облачный пользователь — это пользователь, не синхронизированный с клиентом посредством AAD Connect. Этот пользователь был создан непосредственно в Azure AD. Используйте командлеты **Get-MsolUser** и **Set-MsolUser** модуля Azure AD для Windows PowerShell, чтобы просмотреть или указать географическое расположение для хранения почтового ящика облачного пользователя.

Чтобы просмотреть значение **PreferredDataLocation** для пользователя, используйте следующий синтаксис в Azure AD PowerShell:

```powershell
Get-MsolUser -UserPrincipalName <UserPrincipalName> | Format-List UserPrincipalName,PreferredDataLocation
```

Например, чтобы посмотреть значение **PreferredDataLocation** для пользователя michelle@contoso.onmicrosoft.com, выполните следующую команду:

```powershell
Get-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com | Format-List
```

Чтобы изменить значение **PreferredDataLocation** для объекта облачного пользователя, используйте следующий синтаксис в Azure AD PowerShell:

```powershell
Set-MsolUser -UserPrincipalName <UserPrincipalName> -PreferredDataLocation <GeoLocationCode>
```

Например, чтобы присвоить значению **PreferredDataLocation** регион Европейского Союза (EUR) для пользователя michelle@contoso.onmicrosoft.com, выполните следующую команду:

```powershell
Set-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com -PreferredDataLocation EUR
```

> [!NOTE]
>
> - Как упоминалось ранее, эту процедуру нельзя использовать для синхронизированных объектов пользователя из локального Active Directory. Нужно изменить значение **PreferredDataLocation** в Active Directory и синхронизировать его с помощью AAD Connect. Дополнительные сведения см. в статье [Синхронизация Azure Active Directory Connect: настройка предпочтительного расположения данных для ресурсов Microsoft 365](/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).
>
> - Продолжительность перемещения почтового ящика в новое географическое расположение зависит от нескольких факторов:
>
>   - Размер и тип почтового ящика.
>   - Число перемещаемых почтовых ящиков.
>   - Доступность ресурсов перемещения.

### <a name="move-an-inactive-mailbox-to-a-specific-geo"></a>Перемещение неактивного почтового ящика в определенный гео

Нельзя перемещать неактивные почтовые ящики, которые сохраняются в целях соответствия требованиям (например, почтовые ящики в удержании судебного разбирательства), изменяя их значение **PreferredDataLocation.** Чтобы переместить неактивный почтовый ящик в другой гео, необходимо сделать следующие действия:

1. Восстановление неактивного почтового ящика. Инструкции см. в [статью Восстановление неактивного почтового ящика.](../compliance/recover-an-inactive-mailbox.md)

2. Запретить помощнику управляемых папок обрабатывать восстановленный почтовый ящик, заменив его именем, псевдонимом, учетной записью или адресом электронной почты почтового ящика и запуская следующую команду в \<MailboxIdentity\> [Exchange Online PowerShell:](/powershell/exchange/connect-to-exchange-online-powershell)

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $true
    ```

3. **Назначьте лицензию Exchange Online Plan 2** на восстановленный почтовый ящик. Этот шаг необходим для того, чтобы вернуть почтовый ящик на удержание судебного разбирательства. Инструкции см. в [инструкции Назначение лицензий пользователям.](../admin/manage/assign-licenses-to-users.md)

4. Настройте **значение PreferredDataLocation** в почтовом ящике, как описано в предыдущем разделе.

5. После подтверждения того, что почтовый ящик переместился в новое географическое расположение, поместите восстановленный почтовый ящик обратно в удержание судебного разбирательства. Инструкции см. в [сообщении Place a mailbox on Litigation Hold.](../compliance/create-a-litigation-hold.md#place-a-mailbox-on-litigation-hold)

6. После проверки на месте удержания судебного разбирательства позвольте помощнику управляемых папок снова обработать почтовый ящик, заменив имя, псевдоним, учетную запись или адрес электронной почты почтового ящика и выпустив следующую команду в \<MailboxIdentity\> [Exchange Online PowerShell:](/powershell/exchange/connect-to-exchange-online-powershell)

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $false
    ```

7. Сделайте почтовый ящик неактивным, удалив учетную запись пользователя, связанную с почтовым ящиком. Инструкции см. в [публикации Delete a user from your organization.](../admin/add-users/delete-a-user.md) Этот шаг также освобождает лицензию Exchange Online Plan 2 для других видов использования.

**Примечание.** При перемещение неактивного почтового ящика в другое географическое расположение может повлиять на результаты поиска контента или возможность поиска почтового ящика из бывшего географического расположения. Дополнительные сведения см. в [материалах Поиска и экспорта контента в средах Multi-Geo.](../compliance/set-up-compliance-boundaries.md#searching-and-exporting-content-in-multi-geo-environments)

## <a name="create-new-cloud-mailboxes-in-a-specific-geo-location"></a>Создание новых облачных почтовых ящиков в определенном географическом расположении

Чтобы создать почтовый ящик в определенном географическом расположении, нужно выполнить одно из следующих действий:

- Настройте значение **PreferredDataLocation,** как описано в предыдущем разделе [Перемещение](#move-an-existing-cloud-only-mailbox-to-a-specific-geo-location) существующего облачного почтового ящика в определенный раздел геолокации перед созданием почтового ящика в Exchange Online.  Например, настройте значение **PreferredDataLocation** для пользователя перед назначением лицензии.

- Назначьте лицензию одновременно с настройкой значения **PreferredDataLocation**.

Чтобы создать облачного лицензированного пользователя (не синхронизированного с помощью AAD Connect) в определенном географическом расположении, используйте следующий синтаксис в Azure AD PowerShell:

```powershell
New-MsolUser -UserPrincipalName <UserPrincipalName> -DisplayName "<Display Name>" [-FirstName <FirstName>] [-LastName <LastName>] [-Password <Password>] [-LicenseAssignment <AccountSkuId>] -PreferredDataLocation <GeoLocationCode>
```

В этом примере создается новая учетная запись пользователя Elizabeth Brunner со следующими значениями:

- Имя участника-пользователя: ebrunner@contoso.onmicrosoft.com
- Имя: Elizabeth
- Фамилия: Brunner
- Отображаемое имя: Elizabeth Brunner
- Пароль: создается случайным образом и отображается в результатах команды (так как не используется параметр *Password*)
- Лицензия: `contoso:ENTERPRISEPREMIUM` (E5)
- Расположение: Австралия (AUS)

```powershell
New-MsolUser -UserPrincipalName ebrunner@contoso.onmicrosoft.com -DisplayName "Elizabeth Brunner" -FirstName Elizabeth -LastName Brunner -LicenseAssignment contoso:ENTERPRISEPREMIUM -PreferredDataLocation AUS
```

Дополнительные сведения о создании учетных записей пользователей и поиске значений LicenseAssignment в Azure AD PowerShell см. в статьях [Создание учетных записей пользователей с помощью PowerShell](create-user-accounts-with-microsoft-365-powershell.md) и [Просмотр лицензий и служб с помощью PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).

> [!NOTE]
> Если вы используете Exchange Online PowerShell, чтобы включить почтовый ящик, и вам нужно создать почтовый ящик непосредственно в географическом расположении, указанном в параметре **PreferredDataLocation**, необходимо использовать командлет Exchange Online, например, **Enable-Mailbox** или **New-Mailbox**, прямо в облачной службе. Если вы используете командлет **Enable-RemoteMailbox** в локальной среде Exchange PowerShell, почтовый ящик будет создан в центральном географическом расположении.

## <a name="onboard-existing-on-premises-mailboxes-in-a-specific-geo-location"></a>Перенос существующих локальных почтовых ящиков в определенное географическое расположение

Можно использовать стандартные средства и процедуры переноса для перемещения почтового ящика из локальной организации Exchange в Exchange Online, включая [информационную панель миграции в Центре администрирования Exchange](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331) и командлет [New-MigrationBatch](/powershell/module/exchange/new-migrationbatch) в Exchange Online PowerShell.

Сначала нужно подтвердить, что объект пользователя существует для каждого переносимого почтового ящика, и проверить правильность значения **PreferredDataLocation**, настроенного в Azure AD. Средства переноса учитывают значение **PreferredDataLocation** и переносят почтовые ящики непосредственно в указанное географическое расположение.

Или можно использовать указанные ниже действия для переноса почтовых ящиков непосредственно в определенное географическое расположение с помощью командлета [New-MoveRequest](/powershell/module/exchange/new-moverequest) в Exchange Online PowerShell.

1. Убедитесь в наличии объекта пользователя для каждого переносимого почтового ящика и в установке нужного значения **PreferredDataLocation** в Azure AD. Значение **PreferredDataLocation** синхронизируется с атрибутом **MailboxRegion** соответствующего объекта пользователя почты в Exchange Online.

2. Напрямую подключитесь к определенному периферийному географическому расположению, следуя инструкциям по подключению, указанным выше в этой статье.

3. В Exchange Online PowerShell сохраните учетные данные локального администратора, использующиеся для выполнения переноса почтового ящика, в переменной, выполнив следующую команду:

   ```powershell
   $RC = Get-Credential
   ```

4. В Exchange Online PowerShell, создайте новый командлет **New-MoveRequest**, как в следующем примере:

   ```powershell
   New-MoveRequest -Remote -RemoteHostName mail.contoso.com -RemoteCredential $RC -Identity user@contoso.com -TargetDeliveryDomain <YourAppropriateDomain>
   ```

5. Повторите шаг 4 для каждого почтового ящика, требующего переноса из локальной среды Exchange в периферийное географическое расположение, к которому вы в настоящее время подключены.

6. Если нужно перенести дополнительные почтовые ящики в другое периферийное географическое расположение, повторите шаги 2–4 для каждого определенного периферийного расположения.

## <a name="multi-geo-reporting"></a>Отчеты об использовании нескольких регионов

**Отчеты об использовании нескольких регионов** в Центре администрирования Microsoft 365 отображают число пользователей по географическим расположениям. Отчет отображает распределение пользователей в текущем месяце и представляет ретроспективные данные за последние 6 месяцев.

## <a name="see-also"></a>См. также

[Управление Microsoft 365 с помощью PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)