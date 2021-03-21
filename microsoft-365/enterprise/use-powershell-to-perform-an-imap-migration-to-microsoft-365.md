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
description: Узнайте, как использовать PowerShell для выполнения миграции протокола доступа к интернет-почте (IMAP) в Microsoft 365.
ms.openlocfilehash: fbfc0340e80ce70aa8a706d89a4d27729b91535b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924772"
---
# <a name="use-powershell-to-perform-an-imap-migration-to-microsoft-365"></a><span data-ttu-id="1ba18-103">Миграция IMAP в Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="1ba18-103">Use PowerShell to perform an IMAP migration to Microsoft 365</span></span>

<span data-ttu-id="1ba18-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="1ba18-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="1ba18-105">В рамках развертывания Microsoft 365 можно перенести содержимое почтовых ящиков пользователей из службы электронной почты протокола доступа к Интернету (IMAP) в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1ba18-105">As part of the process of deploying Microsoft 365, you can choose to migrate the contents of user mailboxes from an Internet Mail Access Protocol (IMAP) email service to Microsoft 365.</span></span> <span data-ttu-id="1ba18-106">В этой статье описаны задачи, которые выполняются при миграции электронной почты IMAP с помощью Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ba18-106">This article walks you through the tasks for an email IMAP migration by using Exchange Online PowerShell.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1ba18-107">Вы также можете использовать центр администрирования Exchange для выполнения миграции IMAP.</span><span class="sxs-lookup"><span data-stu-id="1ba18-107">You can also use the Exchange admin center to perform an IMAP migration.</span></span> <span data-ttu-id="1ba18-108">См. [миграцию почтовых ящиков IMAP.](/Exchange/mailbox-migration/migrating-imap-mailboxes/migrating-imap-mailboxes)</span><span class="sxs-lookup"><span data-stu-id="1ba18-108">See [Migrate your IMAP mailboxes](/Exchange/mailbox-migration/migrating-imap-mailboxes/migrating-imap-mailboxes).</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1ba18-109">Что нужно знать перед началом работы?</span><span class="sxs-lookup"><span data-stu-id="1ba18-109">What do you need to know before you begin?</span></span>

<span data-ttu-id="1ba18-110">Предполагаемое время для выполнения этой задачи: 2-5 минут для создания пакета миграции.</span><span class="sxs-lookup"><span data-stu-id="1ba18-110">Estimated time to complete this task: 2-5 minutes to create a migration batch.</span></span> <span data-ttu-id="1ba18-111">После запуска пакета миграции продолжительность миграции будет зависеть от количества почтовых ящиков в пакете, размера каждого почтового ящика и доступной пропускной способности сети.</span><span class="sxs-lookup"><span data-stu-id="1ba18-111">After the migration batch is started, the duration of the migration will vary based on the number of mailboxes in the batch, the size of each mailbox, and your available network capacity.</span></span> <span data-ttu-id="1ba18-112">Сведения о других факторах, влияющих на время переноса почтовых ящиков в Microsoft 365, см. в см. [в руб.](/Exchange/mailbox-migration/office-365-migration-best-practices)</span><span class="sxs-lookup"><span data-stu-id="1ba18-112">For information about other factors that affect how long it takes to migrate mailboxes to Microsoft 365, see [Migration Performance](/Exchange/mailbox-migration/office-365-migration-best-practices).</span></span>
  
<span data-ttu-id="1ba18-p104">Для выполнения этой процедуры (процедур) необходимы соответствующие разрешения. Сведения о необходимых разрешениях см. в пункте "Миграция" статьи [Разрешения получателей](/exchange/recipients-permissions-exchange-2013-help) в соответствующей таблице.</span><span class="sxs-lookup"><span data-stu-id="1ba18-p104">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Migration" entry in a table in the [Recipients Permissions](/exchange/recipients-permissions-exchange-2013-help) topic.</span></span>
  
<span data-ttu-id="1ba18-p105">Чтобы использовать командлеты Exchange Online PowerShell, вам необходимо войти в систему и импортировать командлеты в локальный сеанс Windows PowerShell. Инструкции см в статье [Подключение к Exchange Online с помощью удаленной оболочки PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="1ba18-p105">To use the Exchange Online PowerShell cmdlets, you need to sign in and import the cmdlets into your local Windows PowerShell session. See [Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) for instructions.</span></span>
  
<span data-ttu-id="1ba18-117">Полный список команд миграции см. в статье [Командлеты перемещения и миграции](/powershell/exchange/).</span><span class="sxs-lookup"><span data-stu-id="1ba18-117">For a full list of migration commands, see [Move and migration cmdlets](/powershell/exchange/).</span></span>
  
<span data-ttu-id="1ba18-118">К миграции IMAP применяются следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="1ba18-118">The following restrictions apply to IMAP migrations:</span></span>
  
- <span data-ttu-id="1ba18-p106">Можно перемещать только элементы из папки "Входящие" и других папок почты. Миграция контактов, элементов календаря и задач невозможна.</span><span class="sxs-lookup"><span data-stu-id="1ba18-p106">Only items in a user's inbox or other mail folders can be migrated. You can't migrate contacts, calendar items, or tasks.</span></span>
    
- <span data-ttu-id="1ba18-121">Из почтового ящика пользователя можно перенести не более 500 000 элементов.</span><span class="sxs-lookup"><span data-stu-id="1ba18-121">A maximum of 500,000 items can be migrated from a user's mailbox.</span></span>
    
- <span data-ttu-id="1ba18-122">Максимальный размер сообщения, которое можно перенести, равен 35 МБ.</span><span class="sxs-lookup"><span data-stu-id="1ba18-122">The maximum message size that can be migrated is 35 MB.</span></span>
    
## <a name="migration-steps"></a><span data-ttu-id="1ba18-123">Шаги миграции</span><span class="sxs-lookup"><span data-stu-id="1ba18-123">Migration steps</span></span>

### <a name="step-1-prepare-for-an-imap-migration"></a><span data-ttu-id="1ba18-124">Шаг 1. Подготовка к миграции IMAP</span><span class="sxs-lookup"><span data-stu-id="1ba18-124">Step 1: Prepare for an IMAP migration</span></span>
<span data-ttu-id="1ba18-125"><a name="BK_Step1"> </a></span><span class="sxs-lookup"><span data-stu-id="1ba18-125"><a name="BK_Step1"> </a></span></span>

- <span data-ttu-id="1ba18-126">**Если у вас есть домен для организации IMAP, добавьте его в качестве принятого домена вашей организации Microsoft 365.**</span><span class="sxs-lookup"><span data-stu-id="1ba18-126">**If you have a domain for you IMAP organization, add it as an accepted domain of your Microsoft 365 organization.**</span></span> <span data-ttu-id="1ba18-127">Если вы хотите использовать тот же домен, который уже принадлежит для почтовых ящиков Microsoft 365, сначала необходимо добавить его в качестве принятого домена в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1ba18-127">If you want to use the same domain you already own for your Microsoft 365 mailboxes, you first have to add it as an accepted domain to Microsoft 365.</span></span> <span data-ttu-id="1ba18-128">После его добавления можно создать пользователей в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1ba18-128">After you have added it, you can create your users in Microsoft 365.</span></span> <span data-ttu-id="1ba18-129">Дополнительные сведения см. в[дополнительных сведениях: Проверка домена.](../admin/setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="1ba18-129">For more information, see[Verify your domain](../admin/setup/add-domain.md).</span></span>
    
- <span data-ttu-id="1ba18-130">**Добавьте каждого пользователя в Microsoft 365, чтобы у них был почтовый ящик.**</span><span class="sxs-lookup"><span data-stu-id="1ba18-130">**Add each user to Microsoft 365 so that they have a mailbox.**</span></span> <span data-ttu-id="1ba18-131">Инструкции см. в[добавлении пользователей в Microsoft 365 для бизнеса.](../admin/add-users/add-users.md)</span><span class="sxs-lookup"><span data-stu-id="1ba18-131">For instructions, see[Add users to Microsoft 365 for business](../admin/add-users/add-users.md).</span></span>
    
- <span data-ttu-id="1ba18-p109">**Получите полное доменное имя (FQDN) сервера IMAP**. Необходимо указать полное доменное имя (FQDN) (которое также называется полным именем компьютера) сервера IMAP, из которого будут переноситься данные почтовых ящиков при создании конечной точки миграции IMAP. С помощью клиента IMAP или команды PING убедитесь, что это имя можно использовать для подключения к серверу IMAP через Интернет.</span><span class="sxs-lookup"><span data-stu-id="1ba18-p109">**Obtain the FQDN of the IMAP server**. You need to provide the fully qualified domain name (FQDN) (also called the full computer name) of the IMAP server that you will migrate mailbox data from when you create an IMAP migration endpoint. Use an IMAP client or the PING command to verify that you can use the FQDN to communicate with the IMAP server over the Internet.</span></span>
    
- <span data-ttu-id="1ba18-p110">**Настройте брандмауэр, разрешив подключения IMAP**. Может потребоваться открыть порты в брандмауэре организации, в которой размещен сервер IMAP, чтобы сетевой трафик, исходящий из центра обработки данных корпорации Майкрософт во время миграции, смог поступать в организацию, в которой размещен сервер IMAP. Список IP-адресов, используемых центрами обработки данных корпорации Майкрософт, см. в статье [URL-адреса и диапазоны IP-адресов Office 365](./urls-and-ip-address-ranges.md).</span><span class="sxs-lookup"><span data-stu-id="1ba18-p110">**Configure the firewall to allow IMAP connections**. You might have to open ports in the firewall of the organization that hosts the IMAP server so network traffic originating from the Microsoft datacenter during the migration is allowed to enter the organization that hosts the IMAP server. For a list of IP addresses used by Microsoft datacenters, see [Exchange Online URLs and IP Address Ranges](./urls-and-ip-address-ranges.md).</span></span>
    
- <span data-ttu-id="1ba18-p111">**Предоставьте учетной записи администратора разрешения на доступа к почтовым ящикам в организации IMAP**. Если в CSV-файле используются учетные данные администратора, применяемая учетная запись должна иметь необходимые разрешения на доступ к локальным почтовым ящикам. Разрешения, необходимые для доступа к почтовым ящикам пользователей, определяются конкретным сервером IMAP.</span><span class="sxs-lookup"><span data-stu-id="1ba18-p111">**Assign the administrator account permissions to access mailboxes in your IMAP organization**. If you use administrator credentials in the CSV file, the account that you use must have the necessary permissions to access the on-premises mailboxes. The permissions required to access user mailboxes is determined by the particular IMAP server.</span></span> 
    
- <span data-ttu-id="1ba18-p112">**Чтобы использовать командлеты Exchange Online PowerShell**, вам необходимо войти в систему и импортировать командлеты в локальный сеанс Windows PowerShell. Инструкции см в статье [Подключение к Exchange Online с помощью удаленной оболочки PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="1ba18-p112">**To use the Exchange Online PowerShell cmdlets**, you need to sign in and import the cmdlets into your local Windows PowerShell session. See [Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) for instructions.</span></span>
    
    <span data-ttu-id="1ba18-143">Полный список команд миграции см. в статье [Командлеты перемещения и миграции](/powershell/exchange/).</span><span class="sxs-lookup"><span data-stu-id="1ba18-143">For a full list of migration commands, see [Move and migration cmdlets](/powershell/exchange/).</span></span>
    
- <span data-ttu-id="1ba18-p113">**Убедитесь, что вы можете подключиться к серверу IMAP**. Выполните следующую команду в Exchange Online PowerShell, чтобы проверить параметры подключения к серверу IMAP.</span><span class="sxs-lookup"><span data-stu-id="1ba18-p113">**Verify that you can connect to your IMAP server**. Run the following command in Exchange Online PowerShell to test the connection settings to your IMAP server.</span></span>
    
  ```powershell
  Test-MigrationServerAvailability -IMAP -RemoteServer <FQDN of IMAP server> -Port <143 or 993> -Security <None, Ssl, or Tls>
  ```

    <span data-ttu-id="1ba18-146">Для параметра **Port** обычно устанавливается значение 143 для незашифрованных или TLS-соединений и значение 993 для SSL-соединений.</span><span class="sxs-lookup"><span data-stu-id="1ba18-146">For the value of the **Port** parameter, it's typical to use 143 for unencrypted or Transport Layer Security (TLS) connections and to use 993 for SSL connections.</span></span>
    
### <a name="step-2-create-a-csv-file-for-an-imap-migration-batch"></a><span data-ttu-id="1ba18-147">Шаг 2. Создание CSV-файла для пакета миграции IMAP.</span><span class="sxs-lookup"><span data-stu-id="1ba18-147">Step 2: Create a CSV file for an IMAP migration batch</span></span>
<span data-ttu-id="1ba18-148"><a name="BK_Step2"> </a></span><span class="sxs-lookup"><span data-stu-id="1ba18-148"><a name="BK_Step2"> </a></span></span>

<span data-ttu-id="1ba18-p114">Определите группу пользователей, миграцию чьих почтовых ящиков следует выполнить с помощью пакета миграции IMAP. Каждая строка в CSV-файле содержит сведения, необходимые для подключения к почтовому ящику в системе обмена сообщениями IMAP.</span><span class="sxs-lookup"><span data-stu-id="1ba18-p114">Identify the group of users whose mailboxes you want to migrate in an IMAP migration batch. Each row in the CSV file contains information necessary to connect to a mailbox in the IMAP messaging system.</span></span>
  
<span data-ttu-id="1ba18-151">Ниже приведены обязательные атрибуты для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="1ba18-151">Here are the required attributes for each user:</span></span> 
  
- <span data-ttu-id="1ba18-152">**EmailAddress** указывает пользовательский ID для почтового ящика Microsoft 365 пользователя.</span><span class="sxs-lookup"><span data-stu-id="1ba18-152">**EmailAddress** specifies the user ID for the user's Microsoft 365 mailbox.</span></span>
    
- <span data-ttu-id="1ba18-153">**UserName**. Задает для учетной записи имя для входа, при помощи которого будет выполняться доступ к почтовому ящику на сервере IMAP.</span><span class="sxs-lookup"><span data-stu-id="1ba18-153">**UserName** specifies the logon name for the account to use to access the mailbox on the IMAP server.</span></span>
    
- <span data-ttu-id="1ba18-154">**Password**. Задает пароль для учетной записи в столбце **UserName**.</span><span class="sxs-lookup"><span data-stu-id="1ba18-154">**Password** specifies the password for the account in the **UserName** column.</span></span>
    
<span data-ttu-id="1ba18-p115">Ниже приведен пример формата CSV-файла. В этом примере выполняется миграция трех почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="1ba18-p115">Here's an example of the format for the CSV file. In this example, three mailboxes are migrated:</span></span>
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams,1091990
annb@contoso.edu,ann.beebe,2111991
paulc@contoso.edu,paul.cannon,3281986
```

<span data-ttu-id="1ba18-157">В качестве значения атрибута **UserName** кроме имени пользователя можно использовать данные учетной записи, для которой назначены необходимые разрешения на доступ к почтовым ящикам на сервере IMAP. Ниже перечислены несколько специальных форматов, используемых для некоторых серверов IMAP.</span><span class="sxs-lookup"><span data-stu-id="1ba18-157">For the **UserName** attribute, in addition to the user name, you can use the credentials of an account that has been assigned the necessary permissions to access mailboxes on the IMAP server, the following are some of the specific formats used for some of the IMAP servers:</span></span>
  
 <span data-ttu-id="1ba18-158">**Microsoft Exchange**</span><span class="sxs-lookup"><span data-stu-id="1ba18-158">**Microsoft Exchange:**</span></span>
  
<span data-ttu-id="1ba18-159">If you're migrating email from the IMAP implementation for Microsoft Exchange, use the format **Domain/Admin_UserName/User_UserName** for the **UserName** attribute in the CSV file.</span><span class="sxs-lookup"><span data-stu-id="1ba18-159">If you're migrating email from the IMAP implementation for Microsoft Exchange, use the format **Domain/Admin_UserName/User_UserName** for the **UserName** attribute in the CSV file.</span></span> <span data-ttu-id="1ba18-160">Let's say you're migrating email from Exchange for Terry Adams, Ann Beebe, and Paul Cannon.</span><span class="sxs-lookup"><span data-stu-id="1ba18-160">Let's say you're migrating email from Exchange for Terry Adams, Ann Beebe, and Paul Cannon.</span></span> <span data-ttu-id="1ba18-161">У вас есть учетная запись администратора почты, где имя пользователя **— mailadmin,** а пароль **— P \@ ssw0rd.**</span><span class="sxs-lookup"><span data-stu-id="1ba18-161">You have a mail administrator account, where the user name is **mailadmin** and the password is **P\@ssw0rd**.</span></span> <span data-ttu-id="1ba18-162">Here's what your CSV file would look like:</span><span class="sxs-lookup"><span data-stu-id="1ba18-162">Here's what your CSV file would look like:</span></span>
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,contoso-students/mailadmin/terry.adams,P@ssw0rd
annb@contoso.edu,contoso-students/mailadmin/ann.beebe,P@ssw0rd
paulc@contoso.edu,contoso-students/mailadmin/paul.cannon,P@ssw0rd
```

 <span data-ttu-id="1ba18-163">**Dovecot**</span><span class="sxs-lookup"><span data-stu-id="1ba18-163">**Dovecot:**</span></span>
  
<span data-ttu-id="1ba18-164">На серверах IMAP, поддерживающих протокол SASL, например Dovecot, используется формат **имя_пользователя\*имя_администратора**, где звездочка ( \* ) является настраиваемым знаком разделения.</span><span class="sxs-lookup"><span data-stu-id="1ba18-164">For IMAP servers that support Simple Authentication and Security Layer (SASL), such as a Dovecot IMAP server, use the format **User_UserName\*Admin_UserName**, where the asterisk ( \* ) is a configurable separator character.</span></span> <span data-ttu-id="1ba18-165">Предположим, вы переносят электронную почту этих же пользователей с сервера IMAP Dovecot с помощью учетных данных администратора **mailadmin** и **P \@ ssw0rd.**</span><span class="sxs-lookup"><span data-stu-id="1ba18-165">Let's say you're migrating those same users' email from a Dovecot IMAP server using the administrator credentials **mailadmin** and **P\@ssw0rd**.</span></span> <span data-ttu-id="1ba18-166">Вот как будет выглядеть CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="1ba18-166">Here's what your CSV file would look like:</span></span>
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams*mailadmin,P@ssw0rd
annb@contoso.edu,ann.beebe*mailadmin,P@ssw0rd
paulc@contoso.edu,paul.cannon*mailadmin,P@ssw0rd
```

 <span data-ttu-id="1ba18-167">**Mirapoint**</span><span class="sxs-lookup"><span data-stu-id="1ba18-167">**Mirapoint:**</span></span>
  
<span data-ttu-id="1ba18-168">При переносе электронной почты с сервера сообщений Mirapoint используйте формат #user **\@ домена #Admin_UserName#** для учетных данных администратора.</span><span class="sxs-lookup"><span data-stu-id="1ba18-168">If you're migrating email from Mirapoint Message Server, use the format **#user\@domain#Admin_UserName#** for the administrator credentials.</span></span> <span data-ttu-id="1ba18-169">Чтобы перенести электронную почту из Mirapoint с помощью учетных данных администратора **mailadmin** и **P \@ ssw0rd,** ваш CSV-файл будет выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="1ba18-169">To migrate email from Mirapoint using the administrator credentials **mailadmin** and **P\@ssw0rd**, your CSV file would look like this:</span></span>
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,#terry.adams@contoso-students.edu#mailadmin#,P@ssw0rd
annb@contoso.edu,#ann.beebe@contoso-students.edu#mailadmin#,P@ssw0rd
paulc@contoso.edu,#paul.cannon@contoso-students.edu#mailadmin#,P@ssw0rd
```

 <span data-ttu-id="1ba18-170">**Courier-IMAP**</span><span class="sxs-lookup"><span data-stu-id="1ba18-170">**Courier IMAP:**</span></span>
  
<span data-ttu-id="1ba18-171">Некоторые исходные системы электронной почты, такие как Courier IMAP, не поддерживают использование учетных данных администратора почтовых ящиков для переноса почтовых ящиков в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1ba18-171">Some source email systems, such as Courier IMAP, don't support using mailbox admin credentials to migrate mailboxes to Microsoft 365.</span></span> <span data-ttu-id="1ba18-172">В таком случае исходную систему электронной почты необходимо настроить на использование виртуальных общих папок.</span><span class="sxs-lookup"><span data-stu-id="1ba18-172">Instead, you can set up your source email system to use virtual shared folders.</span></span> <span data-ttu-id="1ba18-173">С помощью виртуальных общих папок вы можете использовать учетные данные администратора почтовых ящиков для доступа к почтовым ящикам пользователей в исходной системе электронной почты.</span><span class="sxs-lookup"><span data-stu-id="1ba18-173">By using virtual shared folders, you can use the mailbox admin credentials to access user mailboxes on the source email system.</span></span> <span data-ttu-id="1ba18-174">Дополнительные сведения о настройке виртуальных общих папок для курьерской IMAP см. в [раздел Общие папки.](https://go.microsoft.com/fwlink/p/?LinkId=398870)</span><span class="sxs-lookup"><span data-stu-id="1ba18-174">For more information about how to configure virtual shared folders for Courier IMAP, see [Shared Folders](https://go.microsoft.com/fwlink/p/?LinkId=398870).</span></span>
  
<span data-ttu-id="1ba18-p120">Чтобы перенести почтовые ящики после настройки виртуальных общих папок в исходной системе электронной почты, в файл миграции необходимо включить необязательный атрибут **UserRoot**. Этот атрибут определяет расположение каждого пользовательского почтового ящика в структуре виртуальных общих папок в исходной системе электронной почты. Например, путь к почтовому ящику пользователя Terry  /users/terry.adams.</span><span class="sxs-lookup"><span data-stu-id="1ba18-p120">To migrate mailboxes after you set up virtual shared folders on your source email system, you have to include the optional attribute **UserRoot** in the migration file. This attribute specifies the location of each user's mailbox in the virtual shared folder structure on the source email system. For example, the path to Terry's mailbox is /users/terry.adams.</span></span>
  
<span data-ttu-id="1ba18-178">Ниже приведен пример CSV-файла, содержащего атрибут **UserRoot**.</span><span class="sxs-lookup"><span data-stu-id="1ba18-178">Here's an example of a CSV file that contains the **UserRoot** attribute:</span></span>
  
```powershell
EmailAddress,UserName,Password,UserRoot
terrya@contoso.edu,mailadmin,P@ssw0rd,/users/terry.adams
annb@contoso.edu,mailadmin,P@ssw0rd,/users/ann.beebe
paulc@contoso.edu,mailadmin,P@ssw0rd,/users/paul.cannon
```

### <a name="step-3-create-an-imap-migration-endpoint"></a><span data-ttu-id="1ba18-179">Шаг 3. Создание конечной точки миграции IMAP</span><span class="sxs-lookup"><span data-stu-id="1ba18-179">Step 3: Create an IMAP migration endpoint</span></span>
<span data-ttu-id="1ba18-180"><a name="BK_Step3"> </a></span><span class="sxs-lookup"><span data-stu-id="1ba18-180"><a name="BK_Step3"> </a></span></span>

<span data-ttu-id="1ba18-181">Для успешной миграции электронной почты Microsoft 365 необходимо подключиться к системе электронной почты и взаимодействовать с ней.</span><span class="sxs-lookup"><span data-stu-id="1ba18-181">To migrate email successfully, Microsoft 365 needs to connect to and communicate with the source email system.</span></span> <span data-ttu-id="1ba18-182">Для этого в Microsoft 365 используется конечная точка миграции.</span><span class="sxs-lookup"><span data-stu-id="1ba18-182">To do this, Microsoft 365 uses a migration endpoint.</span></span> <span data-ttu-id="1ba18-183">Конечная точка миграции также определяет количество почтовых ящиков для одновременной миграции и для одновременной синхронизации в процессе добавочной синхронизации, которая осуществляется один раз каждые 24 часа.</span><span class="sxs-lookup"><span data-stu-id="1ba18-183">The migration endpoint also defines the number of mailboxes to migrate simultaneously and the number of mailboxes to synchronize simultaneously during incremental synchronization, which occurs once every 24 hours.</span></span> <span data-ttu-id="1ba18-184">Чтобы создать конечную точку миграции IMAP, сначала [подключитесь к Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="1ba18-184">To create a migration end point for IMAP migration, first [connect to Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> 
  
<span data-ttu-id="1ba18-185">Полный список команд миграции см. в статье [Командлеты перемещения и миграции](/powershell/exchange/).</span><span class="sxs-lookup"><span data-stu-id="1ba18-185">For a full list of migration commands, see [Move and migration cmdlets](/powershell/exchange/).</span></span>
  
<span data-ttu-id="1ba18-186">Чтобы создать конечную точку миграции IMAP с именем IMAPEndpoint в Exchange Online PowerShell, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="1ba18-186">To create the IMAP migration endpoint called "IMAPEndpoint" in Exchange Online PowerShell, run the following command:</span></span>
  
```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 993 -Security Ssl

```

<span data-ttu-id="1ba18-p122">Вы также можете добавить параметры, чтобы указать одновременно выполняемые миграции (в том числе добавочные) и используемый порт. Следующая команда Exchange Online PowerShell создает конечную точку миграции IMAP с именем IMAPEndpoint, которая поддерживает 50 одновременных миграций и до 25 одновременных добавочных синхронизаций. В этом примере конечная точка также настраивается на использование порта 143 для шифрования TLS.</span><span class="sxs-lookup"><span data-stu-id="1ba18-p122">You can also add parameters to specify concurrent migrations, concurrent incremental migrations, and the port to use. The following Exchange Online PowerShell command creates an IMAP migration endpoint called "IMAPEndpoint" that supports 50 concurrent migrations and up to 25 concurrent incremental synchronizations. It also configures the endpoint to use port 143 for TLS encryption.</span></span>
  
```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 143 -Security Tls -MaxConcurrentMigrations
50 -MaxConcurrentIncrementalSyncs 25
```

<span data-ttu-id="1ba18-190">Дополнительные сведения о командлете **New-MigrationEndpoint** см. в статье [New-MigrationEndpoint](/powershell/module/exchange/new-migrationendpoint).</span><span class="sxs-lookup"><span data-stu-id="1ba18-190">For more information about the **New-MigrationEndpoint** cmdlet, see[New-MigrationEndpoint](/powershell/module/exchange/new-migrationendpoint).</span></span>
  
#### <a name="verify-it-worked"></a><span data-ttu-id="1ba18-191">Проверка работы</span><span class="sxs-lookup"><span data-stu-id="1ba18-191">Verify it worked</span></span>

<span data-ttu-id="1ba18-192">Выполните следующую команду в Exchange Online PowerShell, чтобы отобразить сведения о конечной точке миграции IMAPEndpoint.</span><span class="sxs-lookup"><span data-stu-id="1ba18-192">Run the following command in Exchange Online PowerShell to display information about the "IMAPEndpoint":</span></span>
  
```powershell
Get-MigrationEndpoint IMAPEndpoint | Format-List EndpointType,RemoteServer,Port,Security,Max*
```

### <a name="step-4-create-and-start-an-imap-migration-batch"></a><span data-ttu-id="1ba18-193">Шаг 4. Создание и запуск пакета миграции IMAP</span><span class="sxs-lookup"><span data-stu-id="1ba18-193">Step 4: Create and start an IMAP migration batch</span></span>
<span data-ttu-id="1ba18-194"><a name="BK_Step4"> </a></span><span class="sxs-lookup"><span data-stu-id="1ba18-194"><a name="BK_Step4"> </a></span></span>

<span data-ttu-id="1ba18-p123">Для создания пакета миграции IMAP можно использовать командлет [New-MigrationBatch](/powershell/module/exchange/new-migrationbatch). Можно создать пакет миграции и запустить его обработку автоматически, включив параметр  _AutoStart_. Кроме того, вы можете создать пакет миграции и запустить его с помощью командлета [Start-MigrationBatch](/powershell/module/exchange/start-migrationbatch).</span><span class="sxs-lookup"><span data-stu-id="1ba18-p123">You can use the [New-MigrationBatch](/powershell/module/exchange/new-migrationbatch) cmdlet to create a migration batch for an IMAP migration. You can create a migration batch and start it automatically by including the _AutoStart_ parameter. Alternatively, you can create the migration batch and then start it afterwards by using the[Start-MigrationBatch](/powershell/module/exchange/start-migrationbatch) cmdlet.</span></span>
  
<span data-ttu-id="1ba18-198">Следующая команда Exchange Online PowerShell автоматически запустит пакет миграции IMAPBatch1 с использованием конечной точки IMAP с именем IMAPEndpoint.</span><span class="sxs-lookup"><span data-stu-id="1ba18-198">The following Exchange Online PowerShell command will automatically start the migration batch called "IMAPBatch1" using the IMAP endpoint called "IMAPEndpoint":</span></span>
  
```powershell
New-MigrationBatch -Name IMAPBatch1 -SourceEndpoint IMAPEndpoint -CSVData ([System.IO.File]::ReadAllBytes("C:\Users\Administrator\Desktop\IMAPmigration_1.csv")) -AutoStart
```

#### <a name="verify-it-worked"></a><span data-ttu-id="1ba18-199">Проверка работы</span><span class="sxs-lookup"><span data-stu-id="1ba18-199">Verify it worked</span></span>

<span data-ttu-id="1ba18-200">Выполните командлет [Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch), чтобы отобразить сведения о пакете миграции IMAPBatch1.</span><span class="sxs-lookup"><span data-stu-id="1ba18-200">Run the [Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch) cmdlet to display information about the "IMAPBatch1":</span></span>
  
```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List
```

<span data-ttu-id="1ba18-201">Вы также можете убедиться, что пакет запущен, выполнив следующую команду.</span><span class="sxs-lookup"><span data-stu-id="1ba18-201">You can also verify that the batch has started by running the following command:</span></span>
  
```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a><span data-ttu-id="1ba18-202">Шаг 5. Маршрут электронной почты в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1ba18-202">Step 5: Route your email to Microsoft 365</span></span>
<span data-ttu-id="1ba18-203"><a name="BK_Step5"> </a></span><span class="sxs-lookup"><span data-stu-id="1ba18-203"><a name="BK_Step5"> </a></span></span>

<span data-ttu-id="1ba18-204">Почтовые системы используют запись DNS, которая называется записью MX, чтобы определять, куда нужно доставить электронную почту.</span><span class="sxs-lookup"><span data-stu-id="1ba18-204">Email systems use a DNS record called an MX record to figure out where to deliver emails.</span></span> <span data-ttu-id="1ba18-205">В процессе миграции электронной почты запись MX указывала на вашу исходную систему электронной почты.</span><span class="sxs-lookup"><span data-stu-id="1ba18-205">During the email migration process, your MX record was pointing to your source email system.</span></span> <span data-ttu-id="1ba18-206">Теперь, когда миграция электронной почты в Microsoft 365 завершена, пришло время указать запись MX в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1ba18-206">Now that the email migration to Microsoft 365 is complete, it's time to point your MX record at Microsoft 365.</span></span> <span data-ttu-id="1ba18-207">Это помогает убедиться, что электронная почта доставляется в почтовые ящики Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1ba18-207">This helps make sure that email is delivered to your Microsoft 365 mailboxes.</span></span> <span data-ttu-id="1ba18-208">Перемещая запись MX, вы также сможете отключить старую систему электронной почты, когда будете готовы сделать это.</span><span class="sxs-lookup"><span data-stu-id="1ba18-208">By moving the MX record, you can also turn off your old email system when you're ready.</span></span> 
  
<span data-ttu-id="1ba18-209">Для многих поставщиков DNS предоставляются отдельные инструкции по изменению записей MX.</span><span class="sxs-lookup"><span data-stu-id="1ba18-209">For many DNS providers, there are specific instructions to change your MX record.</span></span> <span data-ttu-id="1ba18-210">Если поставщик DNS не включен или вы хотите получить общее направление, также предоставляются общие инструкции по записи [MX.](https://go.microsoft.com/fwlink/?LinkId=397449)</span><span class="sxs-lookup"><span data-stu-id="1ba18-210">If your DNS provider isn't included, or if you want to get a sense of the general directions, [general MX record instructions ](https://go.microsoft.com/fwlink/?LinkId=397449) are provided as well.</span></span>
  
<span data-ttu-id="1ba18-p126">Системам электронной почты клиентов и партнеров может потребоваться до 72 часов, чтобы распознать измененную запись MX. Подождите по крайней мере 72 часа, прежде чем перейти к следующей задаче: Шаг 6. Удаление пакета миграции IMAP.</span><span class="sxs-lookup"><span data-stu-id="1ba18-p126">It can take up to 72 hours for the email systems of your customers and partners to recognize the changed MX record. Wait at least 72 hours before you proceed to the next task: Step 6: Delete IMAP migration batch.</span></span> 
  
### <a name="step-6-delete-imap-migration-batch"></a><span data-ttu-id="1ba18-213">Шаг 6. Удаление пакета миграции IMAP</span><span class="sxs-lookup"><span data-stu-id="1ba18-213">Step 6: Delete IMAP migration batch</span></span>
<span data-ttu-id="1ba18-214"><a name="BK_Step6"> </a></span><span class="sxs-lookup"><span data-stu-id="1ba18-214"><a name="BK_Step6"> </a></span></span>

<span data-ttu-id="1ba18-215">После изменения записи MX и проверки того, что вся электронная почта передается в почтовые ящики Microsoft 365, уведомите пользователей о том, что их почта будет отправлена в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1ba18-215">After you change the MX record and verify that all email is being routed to Microsoft 365 mailboxes, notify the users that their mail is going to Microsoft 365.</span></span> <span data-ttu-id="1ba18-216">Затем можно удалить пакет миграции IMAP.</span><span class="sxs-lookup"><span data-stu-id="1ba18-216">After this, you can delete the IMAP migration batch.</span></span> <span data-ttu-id="1ba18-217">Убедитесь в следующем, прежде чем удалить пакет миграции.</span><span class="sxs-lookup"><span data-stu-id="1ba18-217">Verify the following before you delete the migration batch.</span></span>
  
- <span data-ttu-id="1ba18-218">Все пользователи используют почтовые ящики Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1ba18-218">All users are using Microsoft 365 mailboxes.</span></span> <span data-ttu-id="1ba18-219">После удаления пакета почта, отправленная в почтовые ящики в локальном Exchange Server не копируется в соответствующие почтовые ящики Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1ba18-219">After the batch is deleted, mail sent to mailboxes on the on-premises Exchange Server isn't copied to the corresponding Microsoft 365 mailboxes.</span></span>
    
- <span data-ttu-id="1ba18-220">Почтовые ящики Microsoft 365 были синхронизированы по крайней мере один раз после начала непосредственной рассылки почты.</span><span class="sxs-lookup"><span data-stu-id="1ba18-220">Microsoft 365 mailboxes were synchronized at least once after mail began being sent directly to them.</span></span> <span data-ttu-id="1ba18-221">Чтобы сделать это, убедитесь, что значение в поле Последнее синхронизированное время для пакета миграции является более последним, чем когда почта начала маршрутизироваться непосредственно в почтовые ящики Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1ba18-221">To do this, make sure that the value in the Last Synced Time box for the migration batch is more recent than when mail started being routed directly to Microsoft 365 mailboxes.</span></span>
    
<span data-ttu-id="1ba18-222">Чтобы удалить пакет миграции IMAPBatch1 в Exchange Online PowerShell, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="1ba18-222">To delete the "IMAPBatch1" migration batch from Exchange Online PowerShell, run the following command:</span></span>
  
```powershell
Remove-MigrationBatch -Identity IMAPBatch1
```

<span data-ttu-id="1ba18-223">Дополнительные сведения о командлете **Remove-MigrationBatch** см. в статье [Remove-MigrationBatch](/powershell/module/exchange/remove-migrationbatch).</span><span class="sxs-lookup"><span data-stu-id="1ba18-223">For more information about the **Remove-MigrationBatch** cmdlet, see[Remove-MigrationBatch](/powershell/module/exchange/remove-migrationbatch).</span></span>
  
#### <a name="verify-it-worked"></a><span data-ttu-id="1ba18-224">Проверка работы</span><span class="sxs-lookup"><span data-stu-id="1ba18-224">Verify it worked</span></span>

<span data-ttu-id="1ba18-225">Выполните следующую команду в Exchange Online PowerShell, чтобы отобразить сведения о пакете миграции IMAPBatch1.</span><span class="sxs-lookup"><span data-stu-id="1ba18-225">Run the following command in Exchange Online PowerShell to display information about the "IMAPBatch1":</span></span>
  
```powershell
Get-MigrationBatch IMAPBatch1"
```

<span data-ttu-id="1ba18-226">Команда либо вернет пакет миграции с состоянием **Удаление**, либо вернет ошибку (не удалось найти пакет миграции), что подтверждает удаление пакета миграции.</span><span class="sxs-lookup"><span data-stu-id="1ba18-226">The command will return either the migration batch with a status of **Removing**, or it will return an error stating that migration batch couldn't be found, verifying that the batch was deleted.</span></span>
  
<span data-ttu-id="1ba18-227">Дополнительные сведения о командлете **Get-MigrationBatch** см. в статье [Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch).</span><span class="sxs-lookup"><span data-stu-id="1ba18-227">For more information about the **Get-MigrationBatch** cmdlet, see[Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1ba18-228">См. также</span><span class="sxs-lookup"><span data-stu-id="1ba18-228">See also</span></span>

[<span data-ttu-id="1ba18-229">Средство устранения неполадок миграции IMAP</span><span class="sxs-lookup"><span data-stu-id="1ba18-229">IMAP Migration Troubleshooter</span></span>](/exchange/troubleshoot/move-or-migrate-mailboxes/troubleshoot-issues-with-imap-mailbox-migration)