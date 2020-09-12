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
description: Сведения о том, как администрировать параметры Multi-Geo Exchange Online в среде Microsoft 365 с помощью PowerShell.
ms.openlocfilehash: 996566d67aa8ba7ebca1406cd5d6265458637fee
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546250"
---
# <a name="administering-exchange-online-mailboxes-in-a-multi-geo-environment"></a>Администрирование почтовых ящиков Exchange Online в среде с поддержкой нескольких регионов

Для просмотра и настройки свойств нескольких регионов в среде Microsoft 365 требуется Exchange Online PowerShell. Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

Вам потребуется [модуль Microsoft Azure Active Directory PowerShell](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) версии 1.1.166.0 или более поздней в версии 1.x, чтобы просматривать свойство **PreferredDataLocation** пользовательских объектов. Для пользовательских объектов, синхронизированных с помощью AAD Connect с AAD, нельзя изменить значение **PreferredDataLocation** непосредственно через AAD PowerShell. Через AAD PowerShell можно изменять объекты облачных пользователей. Сведения о подключении к Azure AD PowerShell см. в статье [Подключение к PowerShell](connect-to-microsoft-365-powershell.md).

## <a name="connect-directly-to-a-geo-location-using-exchange-online-powershell"></a>Прямое подключение к географическому расположению с помощью Exchange Online PowerShell

Обычно Exchange Online PowerShell подключается к центральному географическому расположению. Но вы также можете подключиться непосредственно к периферийному географическому расположению. В связи с повышением производительности рекомендуется подключаться непосредственно к периферийному географическому расположению, если вы управляете пользователями только в этом расположении.

Требования для установки и использования модуля EXO V2 описаны в статье [Установка и обслуживание модуля EXO V2](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).

Чтобы подключить Exchange Online PowerShell к определенному географическому расположению, параметр *ConnectionURI* отличается от стандартных инструкций подключения. Остальные команды и значения совпадают.

В частности, необходимо добавить `?email=<emailaddress>` значение в конец значения _ConnectionURI_ . `<emailaddress>` адрес электронной почты **любого** почтового ящика в целевом географическом расположении. Ваши разрешения для этого почтового ящика или отношения с вашими учетными данными не являются факторами; адрес электронной почты просто сообщает Exchange Online PowerShell, к которой необходимо подключиться.

Пользователям Microsoft 365 или Microsoft 365 GCC обычно не требуется использовать параметр _ConnectionURI_ для подключения к Exchange Online PowerShell. Но чтобы подключиться к определенному географическому расположению, необходимо использовать параметр _ConnectionURI_ , чтобы можно было использовать `?email=<emailaddress>` его в значении.

### <a name="connect-to-a-geo-location-in-exchange-online-powershell-using-multi-factor-authentication-mfa"></a>Подключение к географическому расположению в Exchange Online PowerShell с использованием многофакторной проверки подлинности (MFA)

1. В окне Windows PowerShell загрузите модуль EXO V2, выполнив следующую команду:

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. В следующем примере admin@contoso.onmicrosoft.com является учетной записью администратора, а целевой географическое расположение — там, где находится olga@contoso.onmicrosoft.com почтового ящика.

  ```powershell
  Connect-ExchangeOnline -UserPrincipalName admin@contoso.onmicrosoft.com -ShowProgress $true -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
  ```

### <a name="connect-to-a-geo-location-in-exchange-online-powershell-without-using-mfa"></a>Подключение к географическому расположению в Exchange Online PowerShell без использования MFA

1. В окне Windows PowerShell загрузите модуль EXO V2, выполнив следующую команду:

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. Выполните следующую команду:

   ```powershell
   $UserCredential = Get-Credential
   ```

   В диалоговом окне **Запрос учетных данных Windows PowerShell** введите название своей рабочей или учебной учетной записи и пароль, а затем нажмите **ОК**.

3. В следующем примере целевое географическое расположение расположено там, где находится olga@contoso.onmicrosoft.com почтовых ящиков.

   ```powershell
   Connect-ExchangeOnline -Credential $UserCredential -ShowProgress $true -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
   ```

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
> Если код географического расположения в имени базы данных не совпадает со значением **маилбоксрегион** , почтовый ящик будет автоматически помещен в очередь перемещения и перемещен в географическое расположение, заданное значением **Маилбоксрегион** (Exchange Online ищет несоответствие между этими значениями свойств).

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
> - Как упоминалось ранее, эту процедуру нельзя использовать для синхронизированных объектов пользователей из локальной службы Active Directory. Нужно изменить значение **PreferredDataLocation** в Active Directory и синхронизировать его с помощью AAD Connect. Дополнительные сведения см. в статье [Синхронизация Azure Active Directory Connect: настройка предпочтительного расположения данных для ресурсов Microsoft 365](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).
>
> - Продолжительность перемещения почтового ящика в новое географическое расположение зависит от нескольких факторов:
>
>   - Размер и тип почтового ящика.
>   - Число перемещаемых почтовых ящиков.
>   - Доступность ресурсов перемещения.

### <a name="move-disabled-mailboxes-that-are-on-litigation-hold"></a>Перемещение отключенных почтовых ящиков, находящихся на судебном удержании

Отключенные почтовые ящики на судебном удержании, сохраненные для целей обнаружения электронных данных, невозможно переместить путем изменения их значения **PreferredDataLocation** в отключенном состоянии. Чтобы переместить отключенный почтовый ящик на судебном удержании:

1. Временно назначьте лицензию для почтового ящика.

2. Измените значение **PreferredDataLocation**.

3. Удалите лицензию из почтового ящика после его перемещения в выбранное географическое расположение, чтобы вернуть его в отключенное состояние.

## <a name="create-new-cloud-mailboxes-in-a-specific-geo-location"></a>Создание новых облачных почтовых ящиков в определенном географическом расположении

Чтобы создать почтовый ящик в определенном географическом расположении, нужно выполнить одно из следующих действий:

- Настройте значение **PreferredDataLocation**, как описано в предыдущем разделе, *перед* созданием почтового ящика в Exchange Online. Например, настройте значение **PreferredDataLocation** для пользователя перед назначением лицензии.

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

Можно использовать стандартные средства и процедуры переноса для перемещения почтового ящика из локальной организации Exchange в Exchange Online, включая [информационную панель миграции в Центре администрирования Exchange](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331) и командлет [New-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) в Exchange Online PowerShell.

Сначала нужно подтвердить, что объект пользователя существует для каждого переносимого почтового ящика, и проверить правильность значения **PreferredDataLocation**, настроенного в Azure AD. Средства переноса учитывают значение **PreferredDataLocation** и переносят почтовые ящики непосредственно в указанное географическое расположение.

Или можно использовать указанные ниже действия для переноса почтовых ящиков непосредственно в определенное географическое расположение с помощью командлета [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) в Exchange Online PowerShell.

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

[Управление Microsoft 365 и Exchange Online с помощью Windows PowerShell](https://support.office.com//article/06a743bb-ceb6-49a9-a61d-db4ffdf54fa6)
