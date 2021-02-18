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
description: Узнайте, как управлять почтовыми пользователями в Exchange Online Protection (EOP), включая использование синхронизации каталогов, EAC и PowerShell для управления пользователями.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6a0dc1c0c343be77c6d6f713ee6b68a08a4fe5be
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289917"
---
# <a name="manage-mail-users-in-standalone-eop"></a>Управление пользователями почты в автономной службе EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
-  [Автономный exchange Online Protection](exchange-online-protection-overview.md)

В автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online почтовые пользователи являются основным типом учетной записи пользователя. Пользователь почты имеет учетные данные учетной записи в вашей автономных организациях EOP и может получать доступ к ресурсам (им назначены разрешения). Адрес электронной почты пользователя почты является внешним (например, в локальной среде электронной почты).

> [!NOTE]
> При создании почтового пользователя соответствующая учетная запись пользователя доступна в Центре администрирования Microsoft 365. При создании учетной записи пользователя в Центре администрирования Microsoft 365 ее нельзя использовать для создания почтового пользователя.

Для создания пользователей почты и управления ими в автономных EOP рекомендуется использовать синхронизацию каталогов, как описано в разделе "Управление почтовыми пользователями" далее в этой статье. [](#use-directory-synchronization-to-manage-mail-users)

Для автономных организаций EOP с небольшим количеством пользователей можно добавлять почтовых пользователей и управлять ими в Центре администрирования Exchange (EAC) или в автономных EOP PowerShell, как описано в этой статье.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Чтобы открыть Центр администрирования Exchange (EAC), см. центр [администрирования Exchange в режиме автономных EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- При создании почтовых пользователей в EOP PowerShell может возникнуть регулирование. Кроме того, командлеты EOP PowerShell используют метод пакетной обработки, который приводит к задержке распространения за несколько минут до того, как будут видны результаты команд.

- Для работы с процедурами, которые данная статья, вам должны быть назначены разрешения в Exchange Online Protection. В частности, необходимы роли **создания** (создания) и **получателей** почты (изменения), которые по умолчанию назначены  группам ролей "Управление организацией" **(глобальные** администраторы) и "Управление получателями". Дополнительные сведения см. в сведениях о разрешениях в автономных [EOP](feature-permissions-in-eop.md) и использовании EAC для изменения списка участников [в группах ролей.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Сведения о сочетаниях клавиш, которые могут применяться к процедурам в этой статье, см. в статье "Сочетания клавиш" для Центра администрирования [Exchange в Exchange Online.](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> Возникли проблемы? Обратитесь за помощью к участникам форумов Exchange. Посетите форум [Exchange Online Protection.](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a>Управление почтовыми пользователями с помощью Центра администрирования Exchange

### <a name="use-the-eac-to-create-mail-users"></a>Создание почтовых пользователей с помощью EAC

1. В EAC перейдите к **контакту** \> **получателя**

2. Щелкните **значок "Новый** ![ новый" ](../../media/ITPro-EAC-AddIcon.png) . На **открываемой странице "Создать** пользователя почты" настройте следующие параметры. Параметры, помеченные <sup>\*</sup> как необходимые.

   - **Имя**

   - **Инициалы:** инициалы человека в середине.

   - **Фамилия**

   - <sup>\*</sup>**Отображаемая** имя: по умолчанию в этом поле отображаются значения из полей **"Имя",**"Инициалы" и "Фамилия".   Вы можете принять это значение или изменить его. Значение должно быть уникальным и иметь максимальную длину 64 символа.

   - <sup>\*</sup>**Псевдоним:** введите уникальный псевдоним (не более 64 символов) для пользователя

   - **Внешний адрес электронной** почты: введите адрес электронной почты пользователя. Домен должен быть внешним для облачной организации.

   - <sup>\*</sup>**ИД пользователя:** введите учетную запись, которую пользователь будет использовать для входа в службу. ИД пользователя состоит из имени пользователя в левой части символа @и домена справа.

   - <sup>\*</sup>**Новый пароль и** <sup>\*</sup> **подтверждение пароля:** введите и повторно введите пароль учетной записи. Убедитесь, что пароль соответствует требованиям организации к длине, сложности и истории пароля.

3. Когда вы закончили, нажмите кнопку **Сохранить**, чтобы создать пользователя почты.

### <a name="use-the-eac-to-modify-mail-users"></a>Использование EAC для изменения почтовых пользователей

1. В Центре администрирования Exchange перейдите в раздел **Получатели** \> **Контакты**.

2. Выберите пользователя почты, который нужно изменить, и нажмите значок  ![ ](../../media/ITPro-EAC-AddIcon.png) редактирования.

3. На открываемой странице свойств пользователя почты щелкните одну из следующих вкладок, чтобы просмотреть или изменить свойства.

   По завершении нажмите кнопку **Сохранить**.

#### <a name="general"></a>Общие

Вкладка **"Общие"** используется для просмотра или изменения базовых сведений о пользователе почты.

- **Имя**

- **Инициалы**

- **Фамилия**

- **Отображаемого** имени : это имя отображается в адресной книге организации, в строках "To" и "From", а также в списке контактов в EAC. Это имя не может содержать пробелы до или после отображаемого имени.

- **ИД пользователя:** это учетная запись пользователя в Microsoft 365. Здесь нельзя изменить это значение.

#### <a name="contact-information"></a>Контактные данные

Используйте **вкладку "Контактные** данные" для просмотра или изменения контактных данных пользователя. Информация на этой странице отображается в адресной книге.

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

Вкладка **"Организация"** используется для записи подробных сведений о роли пользователя в организации.

- **Title**
- **Department**
- **Company**

### <a name="use-the-eac-to-remove-mail-users"></a>Удаление почтовых пользователей с помощью EAC

1. В Центре администрирования Exchange перейдите в раздел **Получатели** \> **Контакты**.

2. Выберите пользователя почты, который нужно удалить, и нажмите значок **"Удалить** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) удалить".

## <a name="use-powershell-to-manage-mail-users"></a>Использование PowerShell для управления почтовыми пользователями

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a>Просмотр пользователей почты с помощью автономных EOP PowerShell

Чтобы получить сводный список всех почтовых пользователей в автономных EOP PowerShell, запустите следующую команду:

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

Чтобы просмотреть подробные сведения об определенном почтовом пользователе, замените его именем, псевдонимом или именем учетной записи и запустите следующие \<MailUserIdentity\> команды:

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

Подробные сведения о синтаксисах и параметрах см. в описании [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) и [Get-User.](https://docs.microsoft.com/powershell/module/exchange/get-user)

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a>Создание почтовых пользователей с помощью автономных EOP PowerShell

Чтобы создать почтовых пользователей в автономных EOP PowerShell, используйте следующий синтаксис:

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

**Примечания**.

- Параметр _Name_ является обязательным, имеет максимальную длину 64 символа и должен быть уникальным. Если вы не используете параметр _DisplayName_, для отображаемого имени указывается значение параметра _Name_.
- Если параметр _Alias_ не используется, для псевдонима используется левая сторона параметра _MicrosoftOnlineServicesID._
- Если параметр _ExternalEmailAddress_ не используется, для внешнего адреса электронной почты используется значение _MicrosoftOnlineServicesID._

В этом примере создается почтовый пользователь со следующими настройками:

- Имя — JeffreyZeng, а отображаемая — "Jeffrey Zeng".
- Имя  Григорий, фамилия  Иванов.
- Псевдоним  gregoryiv.
- Внешний адрес электронной почты  givanov@tailspintoys.com.
- Имя учетной записи jeffreyz@contoso.onmicrosoft.com.
- Пароль  Pa$$word1.

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

Подробные сведения о синтаксисе и параметрах см. в описании [New-EOPMailUser.](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser)

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a>Использование автономных EOP PowerShell для изменения почтовых пользователей

Чтобы изменить существующих почтовых пользователей в автономных EOP PowerShell, используйте следующий синтаксис:

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

Подробные сведения о синтаксисе и параметрах см. в описании [Set-EOPMailUser.](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser)

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a>Использование автономных EOP PowerShell для удаления почтовых пользователей

Чтобы удалить почтовых пользователей в автономных EOP PowerShell, замените имя, псевдоним или имя учетной записи почтового пользователя и запустите \<MailUserIdentity\> следующую команду:

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

В этом примере удаляется пользователь почты пользователя Jeffrey Zeng.

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

Подробные сведения о синтаксисе и параметрах см. в описании [remove-EOPMailUser.](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser)

## <a name="how-do-you-know-these-procedures-worked"></a>Как проверить, что эти процедуры выполнены?

Чтобы убедиться, что вы успешно создали, изменили или удалили почтовых пользователей в автономных EOP, используйте любую из следующих процедур:

- В Центре администрирования Exchange перейдите в раздел **Получатели** \> **Контакты**. Убедитесь, что почтовый пользователь указан (или не указан). Выберите пользователя почты и просмотреть сведения в  области сведений или нажмите значок редактирования, ![ чтобы ](../../media/ITPro-EAC-AddIcon.png) просмотреть параметры.

- В автономных EOP PowerShell запустите следующую команду, чтобы убедиться, что почтовый пользователь указан (или не указан):

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- Замените имя, псевдоним или имя учетной записи почтового пользователя и запустите следующие команды для проверки \<MailUserIdentity\> параметров:

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a>Управление почтовыми пользователями с помощью синхронизации службы каталогов

В автономных EOP синхронизация службы каталогов доступна пользователям с локальной службой Active Directory. Вы можете синхронизировать эти учетные записи с Azure Active Directory (Azure AD), где копии учетных записей хранятся в облаке. При синхронизации существующих учетных записей пользователей с Azure Active Directory их можно просмотреть в области получателей в Центре администрирования Exchange (EAC) или в автономных службах EOP PowerShell. 

**Примечания**.

- Если вы используете синхронизацию службы каталогов для управления получателями, вы по-прежнему можете добавлять пользователей и управлять ими в Центре администрирования Microsoft 365, но они не будут синхронизированы с локальной службой Active Directory. Это объясняется тем, что получатели синхронизируются только в одном направлении: из локальной службы каталогов Active Directory в облако.

- Синхронизацию службы каталогов рекомендуется использовать с такими функциями:

  - **Списки** надежных и заблокированных отправитель Outlook: при синхронизации со службой эти списки будут иметь приоритет над фильтрацией нежелательной почты в службе. Это позволяет пользователям управлять собственным списком надежных и заблокированных отправитель с помощью отдельных записей отправитель и домен. Дополнительные сведения см. в разделе [Настройка параметров нежелательной почты в почтовых ящиках Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md).

  - Пограмная блокировка на основе каталогов **(DBEB).** Дополнительные сведения о DBEB см. в этой теме, чтобы отклонить сообщения, отправленные недопустимым [получателям.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)

  - **Доступ конечных пользователей** к карантину: чтобы получить доступ к своим сообщениям на карантине, получатели должны иметь действительный ИД пользователя и пароль в службе. Дополнительные сведения о карантине см. в записи поиска и освобождения сообщений из карантина от [пользователя.](find-and-release-quarantined-messages-as-a-user.md)

  - Правила потока обработки почты (также известные как правила **транспорта):** при использовании синхронизации службы каталогов существующие пользователи и группы Active Directory автоматически загружаются в облако, и вы можете создать правила потока обработки почты, которые будут ориентированы на определенных пользователей и/или группы, не добавляя их в службу вручную. Обратите [внимание, что](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) динамические группы рассылки нельзя синхронизировать с помощью синхронизации каталогов.

Получите необходимые разрешения и подготовьтесь к синхронизации службы каталогов, как описано в описании гибридного удостоверения [с Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity)

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a>Синхронизация каталогов с помощью Azure Active Directory Connect (AAD Connect)

1. Активация синхронизации службы каталогов, как описано в синхронизации [Azure AD Connect: понимание и настройка синхронизации.](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)

2. Установка и настройка локального компьютера для запуска AAD Connect, как описано в предварительных условия [для Azure AD Connect.](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)

3. [Выберите тип установки, который будет применяться для Azure AD Connect:](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation)

   - [Express](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [Custom](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [Сквозная проверка подлинности](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> Когда Мастер настройки средства синхронизации Azure Active Directory завершит работу, учетная запись **MSOL_AD_SYNC** будет создана в вашем лесу Active Directory. Она используется для чтения и синхронизации локальных данных Active Directory. Чтобы каталоги синхронизировались правильно, убедитесь, что порт TCP 443 на локальном сервере синхронизации службы каталогов открыт.

После настройки синхронизации убедитесь, что AAD Connect синхронизируется правильно. В Центре администрирования Exchange перейдите в раздел **Получатели** \> **Контакты** и убедитесь, что список пользователей с локальной среды должным образом синхронизирован.
