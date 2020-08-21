---
title: Управление пользователями почты в автономном EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: Узнайте об управлении почтовыми пользователями в Exchange Online Protection (EOP), в том числе с использованием синхронизации службы каталогов, EAC и PowerShell для управления пользователями.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 64b7effadd96b6dc025677139c4303acd538dadb
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827079"
---
# <a name="manage-mail-users-in-standalone-eop"></a>Управление пользователями почты в автономном EOP

В автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online почтовые ящики пользователей почты являются основным типом учетных записей пользователей. У пользователя почты есть учетные данные в вашей автономной организации EOP, и он может обращаться к ресурсам (иметь назначенные разрешения). Электронный адрес пользователя почты является внешним (например, в локальной почтовой среде).

> [!NOTE]
> При создании почтового пользователя соответствующая учетная запись пользователя будет доступна в Центре администрирования Microsoft 365. При создании учетной записи пользователя в Центре администрирования Microsoft 365 невозможно использовать эту учетную запись для создания пользователя почты.

Рекомендуемый метод создания почтовых пользователей в автономной службе EOP [Use directory synchronization to manage mail users](#use-directory-synchronization-to-manage-mail-users) и управления ими — использование синхронизации службы каталогов, описанное далее в этом разделе.

Для отдельных организаций EOP с небольшим количеством пользователей можно добавлять почтовых пользователей и управлять ими в Центре администрирования Exchange (EAC) или автономной среде PowerShell EOP, как описано в этой статье.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Чтобы открыть Центр администрирования Exchange ,см. раздел [Центра администрирования Exchange в автономной службе EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- При создании почтовых пользователей в PowerShell в службе EOP вы можете столкнуться с регулированием. Кроме того, командлеты PowerShell в EOP используют метод пакетной обработки, из-за чего результаты команд будут видны через несколько минут.

- Чтобы вы могли выполнить эти процедуры, вам должны быть назначены соответствующие разрешения. В частности, требуются роли создания (создания) и получателей почты (изменение), которые по умолчанию назначаются группам ролей OrganizationManagement (глобальные администраторы) и RecipientManagement. Дополнительные сведения см. в разделе ["Разрешения в автономной службе EOP"](feature-permissions-in-eop.md) и использовании Центра администрирования [Exchange для изменения списка членов в группах ролей.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Сочетания клавиш для процедур, описанных в этой статье, приведены в разделе сочетания клавиш для [Центра администрирования Exchange в Exchange Online.](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> Возникли проблемы? Обратитесь за помощью к участникам форумов Exchange. Посетите [форум по Exchange Online Protection.](https://go.microsoft.com/fwlink/p/?linkId=285351)

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a>Управление почтовыми пользователями с помощью Центра администрирования Exchange

### <a name="use-the-eac-to-create-mail-users"></a>Создание почтовых пользователей с помощью Центра администрирования Exchange

1. В Центре администрирования Exchange перейдите к **разделу "Получатели"** \> **Contacts**

2. Щелкните **значок** ![ ](../../media/ITPro-EAC-AddIcon.png) "Создать". На **открывшейся странице "Новый** пользователь почты" настройте следующие параметры. Обязательными являются <sup>\*</sup> параметры.

   - **Имя**

   - **Инициалы:** отчество человека.

   - **Фамилия**

   - <sup>\*</sup>**Отображаемое имя:** по умолчанию в этом поле отображаются значения из полей **"Имя",** **"Инициализация"** и **"Фамилия".** Можно принять это или изменить его. Значение должно быть уникальным и иметь длину не более 64 символов.

   - <sup>\*</sup>**Псевдоним:** введите уникальный псевдоним пользователя, используя до 64 символов.

   - **Внешний адрес электронной**почты: введите электронный адрес пользователя. Домен должен быть внешним по облачной организации.

   - <sup>\*</sup>**Идентификатор пользователя:** введите учетную запись, которую пользователь будет использовать для входа в службу. Идентификатор состоит из имени пользователя слева от знака @и домена справа от нее.

   - <sup>\*</sup>**Новый пароль и** <sup>\*</sup> **подтверждение пароля:** введите пароль и снова введите пароль учетной записи. Убедитесь, что пароль удовлетворяет требованиям вашей организации к длине, сложности и истории паролей.

3. Когда вы закончили, нажмите кнопку **Сохранить**, чтобы создать пользователя почты.

### <a name="use-the-eac-to-modify-mail-users"></a>Изменение почтовых пользователей с помощью Центра администрирования Exchange

1. В Центре администрирования Exchange перейдите в раздел **Получатели** \> **Контакты**.

2. Выберите пользователя почты, которого необходимо изменить, и нажмите значок **Edit** ![ "Изменить" и значок ](../../media/ITPro-EAC-AddIcon.png) "Изменить".

3. На открывшейся странице свойств пользователя почты щелкните одну из следующих вкладок, чтобы просмотреть или изменить свойства.

   Выполнив необходимые действия, нажмите кнопку **Сохранить**.

#### <a name="general"></a>Общие

Вкладка **"Общие"** позволяет просматривать или изменять основные сведения о пользователе почты.

- **Имя**

- **Инициалы**

- **Фамилия**

- **Отображаемое имя:** это имя будет отображаться в адресной книге, в поле "Кому" "От" в электронной почте и в списке контактов в Центре администрирования Exchange (EAC). Это имя не может содержать пробелы до или после отображаемого имени.

- **Идентификатор пользователя:** это учетная запись пользователя в Microsoft 365. Это значение здесь невозможно изменить.

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

На **вкладке "Организация"** можно указывать подробные сведения о роли пользователя в организации.

- **Название**
- **Department**
- **Company**

### <a name="use-the-eac-to-remove-mail-users"></a>Использование Центра администрирования Exchange для удаления почтовых пользователей

1. В Центре администрирования Exchange перейдите в раздел **Получатели** \> **Контакты**.

2. Выберите пользователя почты, которого необходимо удалить, и нажмите значок **Remove** ![ "Удалить". ](../../media/ITPro-EAC-RemoveIcon.gif)

## <a name="use-powershell-to-manage-mail-users"></a>Управление почтовыми пользователями с помощью PowerShell

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a>Просмотр почтовых пользователей с помощью автономной оболочки EOP PowerShell

Чтобы получить сводный список всех пользователей почты в изолированной службе EOP PowerShell, выполните следующую команду.

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

Чтобы просмотреть подробные сведения об определенном пользователе почты, замените именем, псевдонимом или \<MailUserIdentity\> учетной записью пользователя почты и выполните следующие команды:

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

Дополнительные сведения о синтаксисе и параметрах см. в [разделах Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) [и Get-User.](https://docs.microsoft.com/powershell/module/exchange/get-user)

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a>Создание почтовых пользователей с помощью автономной службы EOP PowerShell

Чтобы создать почтовых пользователей в изолированной службе EOP PowerShell, используйте следующий синтаксис:

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

**Примечания**:

- Параметр _Name_ является обязательным, его длина не должна превышать 64 символа и быть уникальным. Если вы не используете параметр _DisplayName_, для отображаемого имени указывается значение параметра _Name_.
- Если параметр Alias не указан, _то_ в качестве псевдонима используется левая часть параметра _MicrosoftOnlineServicesID._
- Если параметр _ExternalEmailAddress_ не используется, значение _MicrosoftOnlineServicesID_ используется в качестве внешнего адреса электронной почты.

В этом примере создается пользователь почты со следующими параметрами:

- Имя Григорий Иван.
- Имя  Григорий, фамилия  Иванов.
- Псевдоним  gregoryiv.
- Внешний адрес электронной почты  givanov@tailspintoys.com.
- Имя учетной записи jeffreyz@contoso.onmicrosoft.com.
- Пароль  Pa$$word1.

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

Дополнительные сведения о синтаксисе и параметрах см. в [разделе New-EOPMailUser.](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser)

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a>Использование автономной оболочки PowerShell для изменения почтовых пользователей

Для изменения существующих почтовых пользователей в автономной службе EOP PowerShell используйте следующий синтаксис:

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

Дополнительные сведения о синтаксисе и параметрах см. в [статье О Set-EOPMailUser.](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser)

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a>Удаление почтовых пользователей с помощью автономной службы EOP PowerShell

Чтобы удалить пользователей почты в автономной службе EOP PowerShell, \<MailUserIdentity\> замените именем, псевдонимом или учетной записью почтового пользователя и выполните следующую команду:

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

В этом примере удаляется пользователь почты для пользователя Григория Ивана.

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

Дополнительные сведения о синтаксисе и параметрах [см. в статье Remove-EOPMailUser.](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser)

## <a name="how-do-you-know-these-procedures-worked"></a>Как проверить, что эти процедуры выполнены?

Чтобы убедиться в том, что в автономной службе EOP успешно создано, изменено или удалено пользователей почты, выполните одну из приведенных ниже процедур.

- В Центре администрирования Exchange перейдите в раздел **Получатели** \> **Контакты**. Убедитесь, что почтовый пользователь входит в список (или нет в списке). Выберите пользователя почты и просмотрите сведения в области сведений или **нажмите** значок ![ редактирования, ](../../media/ITPro-EAC-AddIcon.png) чтобы просмотреть параметры.

- В автономной службе EOP PowerShell выполните следующую команду, чтобы убедиться, что почтовый пользователь добавлен в список (или нет в списке):

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- Замените \<MailUserIdentity\> именем, псевдонимом или учетной записью пользователя почты и выполните следующие команды для проверки параметров:

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a>Управление почтовыми пользователями с помощью синхронизации службы каталогов

В автономной службе EOP синхронизация каталогов доступна пользователям, использующих локальную службу Active Directory. Вы можете синхронизировать эти учетные записи с Azure Active Directory (Azure AD), где копии учетных записей хранятся в облаке. При синхронизации существующих учетных записей с Azure Active Directory **Recipients** вы можете просматривать соответствующих пользователей в области получателей Центра администрирования Exchange (EAC) или автономной службе EOP PowerShell.

**Примечания**:

- Если для управления получателями используется синхронизация службы каталогов, пользователей можно добавлять и управлять ими в Центр администрирования Microsoft 365, однако они не будут синхронизироваться с локальной службой Active Directory. Это объясняется тем, что получатели синхронизируются только в одном направлении: из локальной службы каталогов Active Directory в облако.

- Синхронизацию службы каталогов рекомендуется использовать с такими функциями:

  - **Списки надежных отправителей и заблокированных отправителей Outlook:** при синхронизации со службой эти списки имеют приоритет над фильтрацией нежелательной почты в службе. Это позволяет пользователям управлять своими собственными списками надежных отправителей и заблокированных отправителей с отдельными записями отправителя и домена. Дополнительные сведения см. в разделе [Настройка параметров нежелательной почты в почтовых ящиках Exchange Online](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes).

  - **Пограничная блокировка на основе каталогов (DBEB):** дополнительные сведения о пограничной блокировке на основе каталогов см. в разделе "Использование пограничной блокировки на основе каталогов" для отклонения [сообщений, отправленных недопустимым получателям.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)

  - **Доступ пользователей к карантине:** чтобы получить доступ к сообщениям, помещенным в карантин, у получателей должен быть действительный идентификатор пользователя и пароль в службе. Дополнительные сведения о карантине см. в разделе ["Поиск и освобождение сообщений на карантине для пользователя".](https://docs.microsoft.com/microsoft-365/security/office-365-security/find-and-release-quarantined-messages-as-a-user)

  - **Правила потока обработки почты (правила транспорта).** При использовании синхронизации службы каталогов существующие пользователи и группы Active Directory автоматически загружаются в облако и затем можно создать правила потока обработки почты для определенных пользователей и/или групп без необходимости добавлять их в службу вручную. Обратите внимание, что [динамические группы рассылки](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) нельзя синхронизировать с синхронизацией службы каталогов.

Получите необходимые разрешения и подготовьтесь к синхронизации службы каталогов, как описано в [статье что такое гибридное удостоверение в Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity)

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a>Синхронизация каталогов с Azure Active Directory Connect (AAD Connect)

1. Активация синхронизации службы каталогов, как описано [в синхронизации Azure AD Connect: анализ синхронизации и настройка их](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)параметров.

2. Установка и настройка локального компьютера для запуска AAD Connect согласно предварительным [требованиям для Azure AD Connect.](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)

3. [Выберите тип установки для Azure AD Connect:](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation)

   - [Express](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [Custom](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [Сквозная проверка подлинности](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> Когда Мастер настройки средства синхронизации Azure Active Directory завершит работу, учетная запись **MSOL_AD_SYNC** будет создана в вашем лесу Active Directory. Она используется для чтения и синхронизации локальных данных Active Directory. Чтобы каталоги синхронизировались правильно, убедитесь, что порт TCP 443 на локальном сервере синхронизации службы каталогов открыт.

После настройки синхронизации убедитесь, что синхронизация в AAD Connect выполняется правильно. В Центре администрирования Exchange перейдите в раздел **Получатели** \> **Контакты** и убедитесь, что список пользователей с локальной среды должным образом синхронизирован.
