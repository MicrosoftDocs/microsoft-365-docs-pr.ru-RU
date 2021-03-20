---
title: Управление пользователями почты в автономной службе EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: Узнайте, как управлять пользователями почты в Exchange Online Protection (EOP), включая использование синхронизации каталогов, EAC и PowerShell для управления пользователями.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 863bde5ef860ee980f768ddc085379180e6a71aa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910622"
---
# <a name="manage-mail-users-in-standalone-eop"></a>Управление пользователями почты в автономной службе EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
-  [Автономный exchange Online Protection](exchange-online-protection-overview.md)

В автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online пользователи почты являются основным типом учетной записи пользователя. Пользователь почты имеет учетные данные учетных записей в вашей автономных организациях EOP и может получать доступ к ресурсам (им назначены разрешения). Адрес электронной почты пользователя является внешним (например, в локальной среде электронной почты).

> [!NOTE]
> При создании почтового пользователя соответствующая учетная запись пользователя доступна в центре администрирования Microsoft 365. При создании учетной записи пользователя в центре администрирования Microsoft 365 вы не можете использовать эту учетную запись для создания почтового пользователя.

Рекомендуемый метод создания и управления пользователями почты в автономных EOP заключается [](#use-directory-synchronization-to-manage-mail-users) в том, чтобы использовать синхронизацию каталогов, как описано в синхронизации каталогов использования, для управления пользователями почты в разделе далее в этой статье.

Для автономных организаций EOP с небольшим числом пользователей можно добавлять и управлять пользователями почты в центре администрирования Exchange (EAC) или в автономных EOP PowerShell, как описано в этой статье.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Чтобы открыть центр администрирования Exchange (EAC), см. в центре администрирования Exchange в режиме [автономный EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- При создании пользователей почты в EOP PowerShell вы можете столкнуться с регулированием. Кроме того, командлеты EOP PowerShell используют метод пакетной обработки, который приводит к задержке распространения за несколько минут до того, как будут видны результаты команд.

- Вам необходимо получить разрешения в Exchange Online Protection, прежде чем вы сможете сделать процедуры в этой статье. В частности, необходимо создать **(создать)** и роли получателей почты (изменить), которые по умолчанию назначены  группам ролей "Управление организацией" **(глобальные** администраторы) и "Управление получателями".  Дополнительные сведения см. в рублях Разрешения в автономных [EOP](feature-permissions-in-eop.md) и Use the EAC изменить список участников [в группах ролей.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Сведения о ярлыках клавиатуры, которые могут применяться к процедурам в этой статье, см. в статье Клавишные ярлыки для центра администрирования Exchange в [Exchange Online.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> Возникли проблемы? Обратитесь за помощью к участникам форумов Exchange. Посетите форум [Exchange Online Protection.](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a>Используйте центр администрирования Exchange для управления пользователями почты

### <a name="use-the-eac-to-create-mail-users"></a>Использование EAC для создания пользователей почты

1. В EAC перейдите к **контактам** \> **получателей**

2. Нажмите **кнопку Новый** ![ значок ](../../media/ITPro-EAC-AddIcon.png) . На **открываемой** странице Пользователя новой почты настройте следующие параметры. Необходимы параметры, <sup>\*</sup> отмеченные с помощью параметра.

   - **Имя**

   - **Инициалы:** средний инициал лица.

   - **Фамилия**

   - <sup>\*</sup>**Отображение имени.** По умолчанию в этом поле отображаются значения из полей **Имя,** **Инициалы** и **Фамилия.** Вы можете принять это значение или изменить его. Значение должно быть уникальным и иметь максимальную длину 64 символа.

   - <sup>\*</sup>**Псевдоним:** Введите уникальный псевдоним с использованием до 64 символов для пользователя

   - **Внешний адрес электронной** почты. Введите адрес электронной почты пользователя. Домен должен быть внешним для облачной организации.

   - <sup>\*</sup>**Пользовательский ID.** Введите учетную запись, которую пользователь будет использовать для входа в службу. Код пользователя состоит из имени пользователя в левой части символа at (@) и домена справа.

   - <sup>\*</sup>**Новый пароль** и <sup>\*</sup> **подтверждение пароля:** введите и повторно введите пароль учетной записи. Убедитесь, что пароль соответствует требованиям к длине, сложности и истории вашей организации.

3. Когда вы закончили, нажмите кнопку **Сохранить**, чтобы создать пользователя почты.

### <a name="use-the-eac-to-modify-mail-users"></a>Использование EAC для изменения пользователей почты

1. В Центре администрирования Exchange перейдите в раздел **Получатели** \> **Контакты**.

2. Выберите пользователя почты, который необходимо изменить, а затем нажмите **кнопку Изменить значок Изменить** ![ ](../../media/ITPro-EAC-AddIcon.png) .

3. На открываемой странице свойств пользователей почты щелкните одну из следующих вкладок, чтобы просмотреть или изменить свойства.

   По завершении нажмите кнопку **Сохранить**.

#### <a name="general"></a>Общие

Используйте **вкладку General** для просмотра или изменения базовых сведений о пользователе почты.

- **Имя**

- **Инициалы**

- **Фамилия**

- **Отображение имени.** Это имя отображается в адресной книге организации, в строках To: и From в электронной почте и в списке контактов в EAC. Это имя не может содержать пробелы до или после отображаемого имени.

- **Пользовательский ID.** Это учетная запись пользователя в Microsoft 365. Вы не можете изменить это значение здесь.

#### <a name="contact-information"></a>Контактные данные

Используйте **вкладку Контактная** информация для просмотра или изменения контактных данных пользователя. Информация на этой странице отображается в адресной книге.

- **Street**
- **City**
- **Область, республика, край, округ**
- **Почтовый индекс**
- **Страна или регион**
- **Рабочий телефон**
- **Мобильный телефон**
- **Fax**
- **Дополнительно**

  - **Office**
  - **Домашний телефон**
  - **Веб-страница**.
  - **Примечания**

#### <a name="organization"></a>Организация

Используйте **вкладку Organization** для записи подробных сведений о роли пользователя в организации.

- **Название**
- **Department**
- **Company**

### <a name="use-the-eac-to-remove-mail-users"></a>Использование EAC для удаления пользователей почты

1. В Центре администрирования Exchange перейдите в раздел **Получатели** \> **Контакты**.

2. Выберите пользователя почты, который необходимо удалить, и нажмите кнопку **Удалить значок Удалить** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .

## <a name="use-powershell-to-manage-mail-users"></a>Использование PowerShell для управления пользователями почты

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a>Использование автономных EOP PowerShell для просмотра пользователей почты

Чтобы вернуть сводный список всех пользователей почты в автономных EOP PowerShell, запустите следующую команду:

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

Чтобы просмотреть подробные сведения о конкретном пользователе почты, замените имя, псевдоним или имя учетной записи пользователя почты и запустите \<MailUserIdentity\> следующие команды:

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

Подробные сведения о синтаксисах и параметрах см. в [сведениях Get-Recipient](/powershell/module/exchange/get-recipient) и [Get-User.](/powershell/module/exchange/get-user)

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a>Использование автономных EOP PowerShell для создания пользователей почты

Чтобы создать пользователей почты в автономных EOP PowerShell, используйте следующий синтаксис:

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

**Примечания.**

- Параметр _Name_ необходим, имеет максимальную длину 64 символа и должен быть уникальным. Если параметр _DisplayName_ не используется, для имени отображения используется значение _параметра Name._
- Если параметр _Alias_ не используется, для псевдонима используется левая сторона параметра _MicrosoftOnlineServicesID._
- Если параметр _ExternalEmailAddress_ не используется, для внешнего адреса электронной почты используется значение _MicrosoftOnlineServicesID._

В этом примере создается пользователь почты со следующими настройками:

- Имя JeffreyZeng и имя отображения — Джеффри Зенг.
- Имя  Григорий, фамилия  Иванов.
- Псевдоним  gregoryiv.
- Внешний адрес электронной почты  givanov@tailspintoys.com.
- Имя учетной записи jeffreyz@contoso.onmicrosoft.com.
- Пароль  Pa$$word1.

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

Подробные сведения о синтаксисе и параметрах см. [в обзоре New-EOPMailUser.](/powershell/module/exchange/new-eopmailuser)

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a>Использование автономных EOP PowerShell для изменения пользователей почты

Чтобы изменить существующие пользователи почты в автономных EOP PowerShell, используйте следующий синтаксис:

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Text>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

В этом примере настраивается внешний адрес электронной почты для пользователя Марты Артемьевой.

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

В этом примере значение "Компания" задано как Contoso для всех почтовых пользователей.

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

Подробные сведения о синтаксисе и параметрах см. [в инструкции Set-EOPMailUser.](/powershell/module/exchange/set-eopmailuser)

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a>Использование автономных EOP PowerShell для удаления пользователей почты

Чтобы удалить пользователей почты в автономных EOP PowerShell, замените имя, псевдоним или имя учетной записи пользователя почты и запустите \<MailUserIdentity\> следующую команду:

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

В этом примере удаляется пользователь почты для Джеффри Зенг.

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

Подробные сведения о синтаксисе и параметрах см. в [ссылке Remove-EOPMailUser.](/powershell/module/exchange/remove-eopmailuser)

## <a name="how-do-you-know-these-procedures-worked"></a>Как проверить, что эти процедуры выполнены?

Чтобы убедиться, что вы успешно создали, изменили или удалили пользователей почты в автономных EOP, используйте любую из следующих процедур:

- В Центре администрирования Exchange перейдите в раздел **Получатели** \> **Контакты**. Убедитесь, что пользователь почты указан (или не указан). Выберите пользователя почты и просмотреть сведения в области Подробные сведения или нажмите **кнопку Изменить** изменить значок, ![ чтобы ](../../media/ITPro-EAC-AddIcon.png) просмотреть параметры.

- В автономных EOP PowerShell запустите следующую команду, чтобы убедиться, что пользователь почты указан (или не указан):

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- Замените имя, псевдоним или имя учетной записи пользователя почты и запустите следующие команды для проверки \<MailUserIdentity\> параметров:

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a>Управление почтовыми пользователями с помощью синхронизации службы каталогов

В автономных EOP синхронизация каталогов доступна для клиентов с локальной службой Active Directory. Эти учетные записи можно синхронизировать с Azure Active Directory (Azure AD), где копии учетных записей хранятся в облаке. При синхронизации существующих учетных записей пользователей с Azure Active Directory эти пользователи можно просмотреть в области получателей центра администрирования Exchange (EAC) или в автономных EOP PowerShell. 

**Примечания.**

- Если для управления получателями используется синхронизация каталогов, можно добавить и управлять пользователями в центре администрирования Microsoft 365, но они не будут синхронизированы с локальной службой Active Directory. Это объясняется тем, что получатели синхронизируются только в одном направлении: из локальной службы каталогов Active Directory в облако.

- Синхронизацию службы каталогов рекомендуется использовать с такими функциями:

  - **Списки безопасного** отправитель Outlook и списки заблокированных отправитель. При синхронизации со службой эти списки будут иметь приоритет над фильтрацией нежелательной почты в службе. Это позволяет пользователям управлять собственным списком безопасного отправитель и список заблокированных отправитель с отдельными отправитель и записей домена. Дополнительные сведения см. в разделе [Настройка параметров нежелательной почты в почтовых ящиках Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md).

  - Дополнительные сведения о **DBEB** см. в тексте Use [Directory Based Edge Blocking to reject messages sent to invalid recipients.](/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)

  - **Конечный доступ** пользователей к карантину. Чтобы получить доступ к их карантинным сообщениям, получатели должны иметь действительный код пользователя и пароль в службе. Дополнительные сведения о карантине см. в сообщении [Find and release quarantined messages as a user.](find-and-release-quarantined-messages-as-a-user.md)

  - Правила потока почты (также известные как правила **транспорта).** При использовании синхронизации каталогов существующие пользователи и группы Active Directory автоматически загружаются в облако, а затем можно создать правила потока почты, которые ориентированы на конкретных пользователей и/или группы, не добавляя их вручную в службу. Обратите [внимание, что динамические](/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) группы рассылки нельзя синхронизировать с помощью синхронизации каталогов.

Получите необходимые разрешения и подготовьтесь к синхронизации каталогов, как описано в описании гибридного удостоверения [с Azure Active Directory?](/azure/active-directory/hybrid/whatis-hybrid-identity).

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a>Синхронизация каталогов с Azure Active Directory Connect (AAD Connect)

1. Активация синхронизации каталогов, как описано в [синхронизации Azure AD Connect: понимание и настройка синхронизации.](/azure/active-directory/hybrid/how-to-connect-sync-whatis)

2. Установка и настройка локального компьютера для запуска AAD Connect, как описано в "Необходимые условия для [подключения Azure AD".](/azure/active-directory/hybrid/how-to-connect-install-prerequisites)

3. [Выберите тип установки, который используется для Подключения Azure AD:](/azure/active-directory/hybrid/how-to-connect-install-select-installation)

   - [Express](/azure/active-directory/hybrid/how-to-connect-install-express)

   - [Custom](/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [Сквозная проверка подлинности](/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> Когда Мастер настройки средства синхронизации Azure Active Directory завершит работу, учетная запись **MSOL_AD_SYNC** будет создана в вашем лесу Active Directory. Она используется для чтения и синхронизации локальных данных Active Directory. Чтобы каталоги синхронизировались правильно, убедитесь, что порт TCP 443 на локальном сервере синхронизации службы каталогов открыт.

После настройки синхронизации убедитесь, что AAD Connect синхронизируется правильно. В Центре администрирования Exchange перейдите в раздел **Получатели** \> **Контакты** и убедитесь, что список пользователей с локальной среды должным образом синхронизирован.