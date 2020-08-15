---
title: Миграция IMAP в Microsoft 365 с помощью PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: c28de4a5-1e8e-4491-9421-af066cde7cdd
description: Узнайте, как использовать PowerShell для миграции протокола IMAP в Microsoft 365.
ms.openlocfilehash: 6eb422455d0bdf31fa1859bd0231b68e5568748c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693376"
---
# <a name="use-powershell-to-perform-an-imap-migration-to-microsoft-365"></a>Миграция IMAP в Microsoft 365 с помощью PowerShell

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

В рамках процесса развертывания Microsoft 365 вы можете перенести содержимое почтовых ящиков пользователей из службы электронной почты IMAP в Microsoft 365. В этой статье описаны задачи, которые выполняются при миграции электронной почты IMAP с помощью Exchange Online PowerShell. 
  
> [!NOTE]
> Вы также можете использовать центр администрирования Exchange для выполнения миграции по протоколу IMAP. Ознакомьтесь [с разнесите свои почтовые ящики IMAP](https://go.microsoft.com/fwlink/p/?LinkId=536685). 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы?

Предполагаемое время выполнения задачи: 2-5 минут для создания пакета миграции. После запуска пакета миграции продолжительность миграции будет зависеть от количества почтовых ящиков в пакете, размера каждого почтового ящика и доступной пропускной способности сети. Сведения о других факторах, влияющих на время переноса почтовых ящиков в Microsoft 365, можно найти в разделе [производительность миграции](https://go.microsoft.com/fwlink/p/?LinkId=275079).
  
Для выполнения этой процедуры (процедур) необходимы соответствующие разрешения. Сведения о необходимых разрешениях см. в пункте "Миграция" статьи [Разрешения получателей](https://go.microsoft.com/fwlink/p/?LinkId=534105) в соответствующей таблице.
  
Чтобы использовать командлеты Exchange Online PowerShell, вам необходимо войти в систему и импортировать командлеты в локальный сеанс Windows PowerShell. Инструкции см в статье [Подключение к Exchange Online с помощью удаленной оболочки PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534121).
  
Полный список команд миграции см. в статье [Командлеты перемещения и миграции](https://go.microsoft.com/fwlink/p/?LinkId=534750).
  
К миграции IMAP применяются следующие ограничения.
  
- Можно перемещать только элементы из папки "Входящие" и других папок почты. Миграция контактов, элементов календаря и задач невозможна.
    
- Из почтового ящика пользователя можно перенести не более 500 000 элементов.
    
- Максимальный размер сообщения, которое можно перенести, равен 35 МБ.
    
## <a name="migration-steps"></a>Шаги миграции

### <a name="step-1-prepare-for-an-imap-migration"></a>Шаг 1. Подготовка к миграции IMAP
<a name="BK_Step1"> </a>

- **Если у вас есть домен для вашей организации IMAP, добавьте его в качестве обслуживаемого домена вашей организации Microsoft 365.** Если вы хотите использовать тот же домен, который вы уже владеете почтовыми ящиками Microsoft 365, сначала необходимо добавить его в качестве обслуживаемого домена в Microsoft 365. После добавления вы можете создавать пользователей в Microsoft 365. Для получения дополнительных сведений обратитесь[к разделу Проверка домена](https://go.microsoft.com/fwlink/p/?LinkId=534110).
    
- **Добавьте каждого пользователя в Microsoft 365, чтобы у них был почтовый ящик.** Инструкции приведены[в статье Добавление пользователей в Microsoft 365 для бизнеса](https://go.microsoft.com/fwlink/p/?LinkId=535065).
    
- **Получите полное доменное имя (FQDN) сервера IMAP**. Необходимо указать полное доменное имя (FQDN) (которое также называется полным именем компьютера) сервера IMAP, из которого будут переноситься данные почтовых ящиков при создании конечной точки миграции IMAP. С помощью клиента IMAP или команды PING убедитесь, что это имя можно использовать для подключения к серверу IMAP через Интернет.
    
- **Настройте брандмауэр, разрешив подключения IMAP**. Может потребоваться открыть порты в брандмауэре организации, в которой размещен сервер IMAP, чтобы сетевой трафик, исходящий из центра обработки данных корпорации Майкрософт во время миграции, смог поступать в организацию, в которой размещен сервер IMAP. Список IP-адресов, используемых центрами обработки данных корпорации Майкрософт, см. в статье [URL-адреса и диапазоны IP-адресов Office 365](https://go.microsoft.com/fwlink/p/?LinkId=535066).
    
- **Предоставьте учетной записи администратора разрешения на доступа к почтовым ящикам в организации IMAP**. Если в CSV-файле используются учетные данные администратора, применяемая учетная запись должна иметь необходимые разрешения на доступ к локальным почтовым ящикам. Разрешения, необходимые для доступа к почтовым ящикам пользователей, определяются конкретным сервером IMAP. 
    
- **Чтобы использовать командлеты Exchange Online PowerShell**, вам необходимо войти в систему и импортировать командлеты в локальный сеанс Windows PowerShell. Инструкции см в статье [Подключение к Exchange Online с помощью удаленной оболочки PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534121).
    
    Полный список команд миграции см. в статье [Командлеты перемещения и миграции](https://go.microsoft.com/fwlink/p/?LinkId=534750).
    
- **Убедитесь, что вы можете подключиться к серверу IMAP**. Выполните следующую команду в Exchange Online PowerShell, чтобы проверить параметры подключения к серверу IMAP.
    
  ```powershell
  Test-MigrationServerAvailability -IMAP -RemoteServer <FQDN of IMAP server> -Port <143 or 993> -Security <None, Ssl, or Tls>
  ```

    Для параметра **Port** обычно устанавливается значение 143 для незашифрованных или TLS-соединений и значение 993 для SSL-соединений.
    
### <a name="step-2-create-a-csv-file-for-an-imap-migration-batch"></a>Шаг 2. Создание CSV-файла для пакета миграции IMAP.
<a name="BK_Step2"> </a>

Определите группу пользователей, миграцию чьих почтовых ящиков следует выполнить с помощью пакета миграции IMAP. Каждая строка в CSV-файле содержит сведения, необходимые для подключения к почтовому ящику в системе обмена сообщениями IMAP.
  
Ниже приведены обязательные атрибуты для каждого пользователя. 
  
- **EmailAddress** — задает идентификатор пользователя для почтового ящика пользователя Microsoft 365.
    
- **UserName**. Задает для учетной записи имя для входа, при помощи которого будет выполняться доступ к почтовому ящику на сервере IMAP.
    
- **Password**. Задает пароль для учетной записи в столбце **UserName**.
    
Ниже приведен пример формата CSV-файла. В этом примере выполняется миграция трех почтовых ящиков.
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams,1091990
annb@contoso.edu,ann.beebe,2111991
paulc@contoso.edu,paul.cannon,3281986
```

В качестве значения атрибута **UserName** кроме имени пользователя можно использовать данные учетной записи, для которой назначены необходимые разрешения на доступ к почтовым ящикам на сервере IMAP. Ниже перечислены несколько специальных форматов, используемых для некоторых серверов IMAP.
  
 **Microsoft Exchange**
  
При переносе электронной почты с реализации IMAP в Microsoft Exchange для атрибута **UserName** в CSV-файле используется формат **домен/имя_администратора/имя_пользователя**. Предположим, выполняется перенос электронной почты Exchange для учетных записей Terry Adams, Ann Beebe и Chris Cannon. Имеется учетная запись администратора почты с именем пользователя **mailadmin** и паролем **P@ssw0rd**. Вот как будет выглядеть CSV-файл.
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,contoso-students/mailadmin/terry.adams,P@ssw0rd
annb@contoso.edu,contoso-students/mailadmin/ann.beebe,P@ssw0rd
paulc@contoso.edu,contoso-students/mailadmin/paul.cannon,P@ssw0rd
```

 **Dovecot**
  
На серверах IMAP, поддерживающих протокол SASL, например Dovecot, используется формат **имя_пользователя*имя_администратора**, где звездочка (*) является настраиваемым знаком разделения. Допустим, переносится почта тех же пользователей с сервера IMAP Dovecot с использованием учетных данных администратора **mailadmin** и **P@ssw0rd**. Вот как будет выглядеть CSV-файл:
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams*mailadmin,P@ssw0rd
annb@contoso.edu,ann.beebe*mailadmin,P@ssw0rd
paulc@contoso.edu,paul.cannon*mailadmin,P@ssw0rd
```

 **Mirapoint**
  
При переносе почты с сервера Mirapoint Message Server для учетных данных администратора используется формат **#пользователь@домен#имя_администратора#**. Для переноса электронной почты с Mirapoint с использованием учетных данных администратора **mailadmin** и **P@ssw0rd** CSV-файл должен выглядеть следующим образом.
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,#terry.adams@contoso-students.edu#mailadmin#,P@ssw0rd
annb@contoso.edu,#ann.beebe@contoso-students.edu#mailadmin#,P@ssw0rd
paulc@contoso.edu,#paul.cannon@contoso-students.edu#mailadmin#,P@ssw0rd
```

 **Courier-IMAP**
  
Некоторые исходные системы электронной почты, например Courier IMAP, не поддерживают использование учетных данных администратора почтового ящика для миграции почтовых ящиков в Microsoft 365. В таком случае исходную систему электронной почты необходимо настроить на использование виртуальных общих папок. С помощью виртуальных общих папок вы можете использовать учетные данные администратора почтовых ящиков для доступа к почтовым ящикам пользователей в исходной системе электронной почты. Для получения дополнительных сведений о настройке виртуальных общих папок для Courier IMAP просмотрите раздел [Общие папки](https://go.microsoft.com/fwlink/p/?LinkId=398870).
  
Чтобы перенести почтовые ящики после настройки виртуальных общих папок в исходной системе электронной почты, в файл миграции необходимо включить необязательный атрибут **UserRoot**. Этот атрибут определяет расположение каждого пользовательского почтового ящика в структуре виртуальных общих папок в исходной системе электронной почты. Например, путь к почтовому ящику пользователя Terry  /users/terry.adams.
  
Ниже приведен пример CSV-файла, содержащего атрибут **UserRoot**.
  
```powershell
EmailAddress,UserName,Password,UserRoot
terrya@contoso.edu,mailadmin,P@ssw0rd,/users/terry.adams
annb@contoso.edu,mailadmin,P@ssw0rd,/users/ann.beebe
paulc@contoso.edu,mailadmin,P@ssw0rd,/users/paul.cannon
```

### <a name="step-3-create-an-imap-migration-endpoint"></a>Шаг 3. Создание конечной точки миграции IMAP
<a name="BK_Step3"> </a>

Для успешной миграции электронной почты в Microsoft 365 необходимо подключиться к исходной почтовой системе и связаться с ней. Для этого в Microsoft 365 используется конечная точка миграции. Конечная точка миграции также определяет количество почтовых ящиков для одновременной миграции и для одновременной синхронизации в процессе добавочной синхронизации, которая осуществляется один раз каждые 24 часа. Чтобы создать конечную точку миграции IMAP, сначала [подключитесь к Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=534121). 
  
Полный список команд миграции см. в статье [Командлеты перемещения и миграции](https://go.microsoft.com/fwlink/p/?LinkId=534750).
  
Чтобы создать конечную точку миграции IMAP с именем IMAPEndpoint в Exchange Online PowerShell, выполните следующую команду.
  
```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 993 -Security Ssl

```

Вы также можете добавить параметры, чтобы указать одновременно выполняемые миграции (в том числе добавочные) и используемый порт. Следующая команда Exchange Online PowerShell создает конечную точку миграции IMAP с именем IMAPEndpoint, которая поддерживает 50 одновременных миграций и до 25 одновременных добавочных синхронизаций. В этом примере конечная точка также настраивается на использование порта 143 для шифрования TLS.
  
```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 143 -Security Tls -MaxConcurrentMigrations
50 -MaxConcurrentIncrementalSyncs 25
```

Дополнительные сведения о командлете **New-MigrationEndpoint** см. в статье[New-MigrationEndpoint](https://go.microsoft.com/fwlink/p/?LinkId=536437).
  
#### <a name="verify-it-worked"></a>Проверка работы

Выполните следующую команду в Exchange Online PowerShell, чтобы отобразить сведения о конечной точке миграции IMAPEndpoint.
  
```powershell
Get-MigrationEndpoint IMAPEndpoint | Format-List EndpointType,RemoteServer,Port,Security,Max*
```

### <a name="step-4-create-and-start-an-imap-migration-batch"></a>Шаг 4. Создание и запуск пакета миграции IMAP
<a name="BK_Step4"> </a>

Для создания пакета миграции IMAP можно использовать командлет [New-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536439). Можно создать пакет миграции и запустить его обработку автоматически, включив параметр  _AutoStart_. Кроме того, вы можете создать пакет миграции и запустить его с помощью командлета [Start-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536440).
  
Следующая команда Exchange Online PowerShell автоматически запустит пакет миграции IMAPBatch1 с использованием конечной точки IMAP с именем IMAPEndpoint.
  
```powershell
New-MigrationBatch -Name IMAPBatch1 -SourceEndpoint IMAPEndpoint -CSVData ([System.IO.File]::ReadAllBytes("C:\Users\Administrator\Desktop\IMAPmigration_1.csv")) -AutoStart
```

#### <a name="verify-it-worked"></a>Проверка работы

Выполните командлет [Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441), чтобы отобразить сведения о пакете миграции IMAPBatch1.
  
```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List
```

Вы также можете убедиться, что пакет запущен, выполнив следующую команду.
  
```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a>Шаг 5: Маршрутизация электронной почты в Microsoft 365
<a name="BK_Step5"> </a>

Почтовые системы используют запись DNS, которая называется записью MX, чтобы определять, куда нужно доставить электронную почту. В процессе миграции электронной почты запись MX указывала на вашу исходную систему электронной почты. После завершения миграции электронной почты в Microsoft 365 настало время указать запись MX в Microsoft 365. Это помогает обеспечить доставку электронной почты в почтовые ящики Microsoft 365. Перемещая запись MX, вы также сможете отключить старую систему электронной почты, когда будете готовы сделать это. 
  
Для многих поставщиков DNS предоставляются отдельные инструкции по изменению записей MX. Если ваш поставщик DNS не включен или вы хотите понять общие указания, также предоставляются [Общие инструкции MX Record ](https://go.microsoft.com/fwlink/?LinkId=397449) .
  
Системам электронной почты клиентов и партнеров может потребоваться до 72 часов, чтобы распознать измененную запись MX. Подождите по крайней мере 72 часа, прежде чем перейти к следующей задаче: Шаг 6. Удаление пакета миграции IMAP. 
  
### <a name="step-6-delete-imap-migration-batch"></a>Шаг 6. Удаление пакета миграции IMAP
<a name="BK_Step6"> </a>

После изменения записи MX и проверки того, что вся электронная почта направляется в почтовые ящики Microsoft 365, уведомите пользователей о том, что их почта переходит в Microsoft 365. Затем можно удалить пакет миграции IMAP. Убедитесь в следующем, прежде чем удалить пакет миграции.
  
- Все пользователи используют почтовые ящики Microsoft 365. После удаления пакета сообщения, отправленные в почтовые ящики на локальном сервере Exchange Server, не копируются в соответствующие почтовые ящики Microsoft 365.
    
- Почтовые ящики Microsoft 365 были синхронизированы по крайней мере один раз после того, как электронная почта сразу же отправляется. Для этого убедитесь, что значение в поле время последней синхронизации для пакета миграции более поздней, чем при маршрутизации почты непосредственно в почтовые ящики Microsoft 365.
    
Чтобы удалить пакет миграции IMAPBatch1 в Exchange Online PowerShell, выполните следующую команду.
  
```powershell
Remove-MigrationBatch -Identity IMAPBatch1
```

Дополнительные сведения о командлете **Remove-MigrationBatch** см. в статье[Remove-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536481).
  
#### <a name="verify-it-worked"></a>Проверка работы

Выполните следующую команду в Exchange Online PowerShell, чтобы отобразить сведения о пакете миграции IMAPBatch1.
  
```powershell
Get-MigrationBatch IMAPBatch1"
```

Команда либо вернет пакет миграции с состоянием **Удаление**, либо вернет ошибку (не удалось найти пакет миграции), что подтверждает удаление пакета миграции.
  
Дополнительные сведения о командлете **Get-MigrationBatch** см. в статье[Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441).
  
## <a name="see-also"></a>См. также

[Средство устранения неполадок миграции IMAP](https://go.microsoft.com/fwlink/p/?LinkId=536482)

