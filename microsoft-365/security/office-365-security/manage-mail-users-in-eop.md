---
title: Управление пользователями почты в автономном EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: Узнайте, как управлять почтовыми пользователями в Exchange Online Protection (EOP), в том числе с помощью синхронизации каталогов, центра администрирования Exchange и PowerShell для управления пользователями.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0e8a4585a16b579c28de719181eed65b65ec6f4f
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352436"
---
# <a name="manage-mail-users-in-standalone-eop"></a>Управление пользователями почты в автономном EOP

В автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online пользователям почты является основной тип учетной записи пользователя. Почтовые пользователи имеют учетные данные в автономной организации EOP и могут получать доступ к ресурсам (назначены разрешения). Адрес электронной почты пользователя является внешним (например, в локальной почтовой среде).

> [!NOTE]
> Когда вы создаете почтового пользователя, соответствующая учетная запись пользователя доступна в центре администрирования Microsoft 365. При создании учетной записи пользователя в центре администрирования Microsoft 365 эту учетную запись невозможно использовать для создания почтового пользователя.

Для создания и управления почтовыми пользователями в автономной EOP рекомендуется использовать синхронизацию службы каталогов, как описано в разделе Использование синхронизации каталогов [для управления почтовыми пользователями](#use-directory-synchronization-to-manage-mail-users) далее в этом разделе.

Для автономных организаций EOP с небольшим количеством пользователей можно добавлять почтовых пользователей и управлять ими в центре администрирования Exchange или в автономной EOP PowerShell, как описано в этом разделе.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Чтобы открыть центр администрирования Exchange, обратитесь к [центру администрирования Exchange в автономной EOP](exchange-admin-center-in-exchange-online-protection-eop.md).

- Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- При создании почтовых пользователей в EOP PowerShell может возникнуть возможность регулирования. Кроме того, командлеты PowerShell EOP используют метод пакетной обработки, который приводит к задержке распространения в течение нескольких минут до того, как результаты команд будут видны.

- Чтобы вы могли выполнить эти процедуры, вам должны быть назначены соответствующие разрешения. В частности, необходимы роли создания получателей почты и получателей почты (изменения), которые назначаются группам ролей Организатионманажемент (глобальные администраторы) и РеЦипиентманажемент по умолчанию. Дополнительные сведения см. [в разделе разрешения в автономных EOP](feature-permissions-in-eop.md) и используйте центр администрирования Exchange для [изменения списка участников в группах ролей](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Дополнительные сведения о сочетаниях клавиш, которые могут применяться к процедурам, описанным в этой статье, приведены в статье [сочетания клавиш для центра администрирования Exchange в Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Возникли проблемы? Обратитесь за помощью к участникам форумов Exchange. Посетите форум [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a>Управление почтовыми пользователями с помощью центра администрирования Exchange

### <a name="use-the-eac-to-create-mail-users"></a>Использование центра администрирования Exchange для создания почтовых пользователей

1. В центре администрирования Exchange выберите **Recipients** \> **Контакты** получателей

2. Нажмите кнопку **создать** ![ новый значок ](../../media/ITPro-EAC-AddIcon.png) . На открывшейся странице **Создание почтового пользователя** настройте указанные ниже параметры. Параметры, отмеченные атрибутом, <sup>\*</sup> являются обязательными.

   - **Имя**

   - **Инициалы**: инициал отчества пользователя.

   - **Фамилия**

   - <sup>\*</sup>**Отображаемое имя**: по умолчанию в этом поле отображаются значения из полей **имя**, **инициалы**и **Фамилия** . Вы можете принять это значение или изменить его. Значение должно быть уникальным и не может быть длиннее 64 символов.

   - <sup>\*</sup>**Alias**: введите уникальный псевдоним для пользователя с длиной до 64 символов.

   - **Внешний адрес электронной почты**: введите адрес электронной почты пользователя. Домен должен быть внешним по отношению к облачной организации.

   - <sup>\*</sup>**Идентификатор пользователя**: введите учетную запись, которую пользователь будет использовать для входа в службу. Идентификатор пользователя состоит из имени пользователя в левой части символа "@" (@) и домена в правой части.

   - <sup>\*</sup>**Новый пароль** и <sup>\*</sup> **Подтверждение пароля**: введите и повторно введите пароль учетной записи. Убедитесь, что пароль соответствует требованиям к длине, сложности и истории паролей вашей организации.

3. Когда вы закончили, нажмите кнопку **Сохранить**, чтобы создать пользователя почты.

### <a name="use-the-eac-to-modify-mail-users"></a>Использование центра администрирования Exchange для изменения почтовых пользователей

1. В Центре администрирования Exchange перейдите в раздел **Получатели** \> **Контакты**.

2. Выберите пользователя почты, которого нужно изменить, а затем щелкните **изменить** ![ значок редактирования ](../../media/ITPro-EAC-AddIcon.png) .

3. На открывшейся странице "Свойства пользователя почты" щелкните одну из следующих вкладок, чтобы просмотреть или изменить свойства.

   По завершении нажмите кнопку **Сохранить**.

#### <a name="general"></a>Общие

Используйте вкладку **Общие** , чтобы просмотреть или изменить основные сведения о почтовом пользователе.

- **Имя**

- **Инициалы**

- **Фамилия**

- **Отображаемое имя**: это имя отображается в адресной книге организации, в строках "Кому:" и "от" в сообщении электронной почты, а также в списке контактов в центре администрирования Exchange. Это имя не может содержать пробелы до или после отображаемого имени.

- **Идентификатор пользователя**: учетная запись пользователя в Microsoft 365. Здесь невозможно изменить это значение.

#### <a name="contact-information"></a>Контактные данные

Используйте вкладку **контактные сведения** , чтобы просмотреть или изменить контактные данные пользователя. Информация на этой странице отображается в адресной книге.

- **Назван**
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

Используйте вкладку **Организация** для записи подробных сведений о роли пользователя в Организации.

- **Title**
- **Department**
- **Company**

### <a name="use-the-eac-to-remove-mail-users"></a>Использование центра администрирования Exchange для удаления почтовых пользователей

1. В Центре администрирования Exchange перейдите в раздел **Получатели** \> **Контакты**.

2. Выберите пользователя почты, которого нужно удалить, а затем нажмите кнопку **Удалить** ![ значок удаления ](../../media/ITPro-EAC-RemoveIcon.gif) .

## <a name="use-powershell-to-manage-mail-users"></a>Управление почтовыми пользователями с помощью PowerShell

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a>Просмотр почтовых пользователей с помощью изолированной EOP PowerShell

Чтобы получить сводный список всех пользователей почты в изолированной EOP PowerShell, выполните следующую команду:

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

Чтобы просмотреть подробные сведения о конкретном почтовом пользователе, замените \< маилусеридентити \> на имя, псевдоним или имя учетной записи пользователя почты, а затем выполните следующие команды:

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) и [Get – User](https://docs.microsoft.com/powershell/module/exchange/get-user).

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a>Создание почтовых пользователей с помощью изолированной EOP PowerShell

Чтобы создавать почтовых пользователей в автономной EOP PowerShell, используйте следующий синтаксис:

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

**Примечания**:

- Параметр _Name_ является обязательным, его длина не должна превышать 64 символов и должна быть уникальной. Если вы не используете параметр _DisplayName_, для отображаемого имени указывается значение параметра _Name_.
- Если вы не используете параметр _Alias_ , для псевдонима используется левая сторона параметра _микрософтонлнесервицесид_ .
- Если параметр _ExternalEmailAddress_ не используется, для внешнего адреса электронной почты используется значение _MicrosoftOnlineServicesID_ .

В этом примере создается пользователь почты со следующими параметрами:

- Имя — Жеффрэйзенг, а отображаемое имя — Джеффри Иванова.
- Имя  Григорий, фамилия  Иванов.
- Псевдоним  gregoryiv.
- Внешний адрес электронной почты  givanov@tailspintoys.com.
- Имя учетной записи — jeffreyz@contoso.onmicrosoft.com.
- Пароль  Pa$$word1.

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

Подробные сведения о синтаксисе и параметрах можно найти в статье [New – EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser).

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a>Изменение почтовых пользователей с помощью изолированной EOP PowerShell

Чтобы изменить существующих почтовых пользователей в изолированной EOP PowerShell, используйте следующий синтаксис:

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Textg>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
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

Подробные сведения о синтаксисе и параметрах можно найти в статье [Set – EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser).

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a>Удаление почтовых пользователей с помощью изолированной EOP PowerShell

Чтобы удалить пользователей почты в изолированной EOP PowerShell, замените \< маилусеридентити \> на имя, псевдоним или имя учетной записи пользователя почты и выполните следующую команду:

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

В этом примере удаляется почтовый пользователь для Джеффри Иванова.

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

Подробные сведения о синтаксисе и параметрах можно найти в статье [Remove – EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser).

## <a name="how-do-you-know-these-procedures-worked"></a>Как проверить, что эти процедуры выполнены?

Чтобы убедиться, что вы успешно создали, изменяли или удалили пользователей почты в автономной EOP, выполните одно из следующих действий:

- В Центре администрирования Exchange перейдите в раздел **Получатели** \> **Контакты**. Убедитесь, что пользователь почты указан (или не указан в списке). Выберите пользователя почты и просмотрите сведения в области сведений или щелкните **изменить** ![ значок редактирования, ](../../media/ITPro-EAC-AddIcon.png) чтобы просмотреть параметры.

- В изолированной EOP PowerShell выполните следующую команду, чтобы убедиться, что пользователь почты указан (или не указан в списке):

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- Замените \< маилусеридентити \> именем, псевдонимом или именем учетной записи пользователя почты и выполните следующие команды, чтобы проверить параметры:

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a>Управление почтовыми пользователями с помощью синхронизации службы каталогов

В автономном режиме EOP синхронизация каталогов доступна для клиентов с локальной службой Active Directory. Вы можете синхронизировать эти учетные записи в Azure Active Directory (Azure AD), где копии учетных записей хранятся в облаке. При синхронизации существующих учетных записей пользователей с Azure Active Directory вы можете просмотреть этих пользователей в области **получателей** в центре администрирования Exchange или в автономной EOP PowerShell.

**Примечания**:

- Если вы используете синхронизацию службы каталогов для управления получателями, вы по-прежнему можете добавлять пользователей в центр администрирования Microsoft 365 и управлять ими, но они не будут синхронизированы с локальной службой Active Directory. Это объясняется тем, что получатели синхронизируются только в одном направлении: из локальной службы каталогов Active Directory в облако.

- Синхронизацию службы каталогов рекомендуется использовать с такими функциями:

  - **Списки надежных отправителей Outlook и заблокированные списки отправителей**: при синхронизации со службой эти списки будут иметь приоритет над фильтрацией нежелательной почты в службе. Это позволяет пользователям управлять собственным списком надежных отправителей и списком заблокированных отправителей с отдельными записями отправителя и домена. Дополнительные сведения см. в разделе [Настройка параметров нежелательной почты в почтовых ящиках Exchange Online](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes).

  - **Пограничная блокировка на основе каталогов (DBEB)**: Дополнительные сведения о DBEB см. [в статье Использование пограничной блокировки на основе каталогов для отклонения сообщений, отправляемых недопустимым получателям](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).

  - **Доступ конечного пользователя к карантину**: чтобы получить доступ к сообщениям, помещенным в карантин, получатели должны иметь действительный идентификатор пользователя и пароль в службе. Для получения дополнительных сведений о карантине обратитесь к разделу [Поиск и освобождение сообщений, помещенных в карантин в качестве пользователя](https://docs.microsoft.com/microsoft-365/security/office-365-security/find-and-release-quarantined-messages-as-a-user).

  - **Правила для поток обработки почты (также называемые правилами транспорта)**: при использовании синхронизации службы каталогов существующие пользователи и группы Active Directory автоматически отправляются в облако, а затем можно создавать правила для обработки почты, предназначенные для определенных пользователей и/или групп, без необходимости вручную добавлять их в службу. Обратите внимание на то, что [динамические группы рассылки](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) невозможно синхронизировать через синхронизацию службы каталогов.

Получите необходимые разрешения и подготовьтесь к синхронизации службы каталогов, как описано в разделе [что такое Гибридная идентификация с Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a>Синхронизация каталогов с помощью Azure Active Directory Connect (AAD Connect)

1. Активируйте синхронизацию службы каталогов, как описано в статье [Azure AD Connect Sync: сведения и Настройка синхронизации](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).

2. Установите и настройте локальный компьютер для запуска подключения AAD, как описано в статье [необходимые условия для Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites).

3. [Выберите тип установки, который будет использоваться для Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation):

   - [Прямых](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [Custom](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [Сквозная проверка подлинности](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> Когда Мастер настройки средства синхронизации Azure Active Directory завершит работу, учетная запись **MSOL_AD_SYNC** будет создана в вашем лесу Active Directory. Она используется для чтения и синхронизации локальных данных Active Directory. Чтобы каталоги синхронизировались правильно, убедитесь, что порт TCP 443 на локальном сервере синхронизации службы каталогов открыт.

После настройки синхронизации обязательно убедитесь, что подключение AAD правильно синхронизируется. В Центре администрирования Exchange перейдите в раздел **Получатели** \> **Контакты** и убедитесь, что список пользователей с локальной среды должным образом синхронизирован.
