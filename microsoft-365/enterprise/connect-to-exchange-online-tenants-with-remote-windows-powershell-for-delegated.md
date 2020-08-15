---
title: Подключение к клиентам Exchange Online с помощью удаленной оболочки Windows PowerShell для партнеров на сайте доступа к данным
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: ''
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
ms.assetid: ae5f1a87-8b77-4f93-a1b8-56f800aeb283
description: Сводка. Использование удаленного сеанса Windows PowerShell для подключения к Exchange Online с помощью значения DelegatedOrg.
ms.openlocfilehash: 1351a6a6d19fac408b673796c1179bca0ede9c9f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693311"
---
# <a name="connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated-access-permissions-dap-partners"></a><span data-ttu-id="17683-103">Подключение к клиентам Exchange Online с помощью удаленного сеанса Windows PowerShell для партнеров службы разрешений делегированного доступа (DAP)</span><span class="sxs-lookup"><span data-stu-id="17683-103">Connect to Exchange Online tenants with remote Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>

<span data-ttu-id="17683-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="17683-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

> [!IMPORTANT]
> <span data-ttu-id="17683-p101">Процедуры, описанные в этой статье, предназначены только для партнеров службы разрешений делегированного доступа (DAP). Если вы не являетесь партнером DAP, не используйте эти процедуры.</span><span class="sxs-lookup"><span data-stu-id="17683-p101">The procedures in this topic are only for Delegated Access Permission (DAP) partners. If you aren't a DAP partner, don't use the procedures in this topic.</span></span> 
  
<span data-ttu-id="17683-107">Партнеры DAP являются партнерами синдикации и поставщиков облачных решений (CSP).</span><span class="sxs-lookup"><span data-stu-id="17683-107">DAP partners are Syndication and Cloud Solution Providers (CSP) partners.</span></span> <span data-ttu-id="17683-108">Они часто являются поставщиками сети или телекоммуникационных услуг в других компаниях.</span><span class="sxs-lookup"><span data-stu-id="17683-108">They are frequently network or telecom providers to other companies.</span></span> <span data-ttu-id="17683-109">Они включают подписки в услуги для своих клиентов.</span><span class="sxs-lookup"><span data-stu-id="17683-109">They bundle subscriptions into their service offerings to their customers.</span></span> <span data-ttu-id="17683-110">Они владеют партнерской арендой, которая автоматически получает права администратора от имени (АОБО) для пользователей Microsoft 365, чтобы они могли администрировать и предоставлять отчеты для всех клиентов клиенты.</span><span class="sxs-lookup"><span data-stu-id="17683-110">They own a partner tenancy that is automatically granted Administer On Behalf Of (AOBO) permissions to their Microsoft 365 customer tenancies so they can administer and report on all of their customer tenancies.</span></span>

<span data-ttu-id="17683-111">Партнеры по настройке доступа к данным могут использовать Exchange Online PowerShell для управления параметрами клиента Exchange Online и получения отчетов Microsoft 365 из командной строки.</span><span class="sxs-lookup"><span data-stu-id="17683-111">DAP partners can use Exchange Online PowerShell to manage customer Exchange Online settings and get Microsoft 365 reports from the command line.</span></span> <span data-ttu-id="17683-112">С помощью Windows PowerShell на локальном компьютере можно создать удаленный сеанс PowerShell с Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="17683-112">You use Windows PowerShell on your local computer to create a remote PowerShell session to Exchange Online.</span></span> <span data-ttu-id="17683-113">Это простой процесс в три этапа, в котором вы вводите свои учетные данные, предоставляете необходимые параметры подключения, а затем импортируете командлеты Exchange Online в локальный сеанс Windows PowerShell, чтобы их можно было использовать.</span><span class="sxs-lookup"><span data-stu-id="17683-113">It's a simple three-step process where you enter your credentials, provide the required connection settings, and then import the Exchange Online cmdlets into your local Windows PowerShell session so that you can use them.</span></span>

> [!NOTE]
> <span data-ttu-id="17683-p104">Партнеры DAP не могут использовать процедуры, описанные в статье [Подключение к Exchange Online PowerShell с помощью многофакторной проверки подлинности](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell), чтобы подключаться к клиентским организациям пользователей в Exchange Online PowerShell. Многофакторная проверка подлинности и удаленный модуль PowerShell в Exchange Online не поддерживают делегированную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="17683-p104">DAP partners can't use the procedures in [Connect to Exchange Online PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell) to connect to their customer tenant organizations in Exchange Online PowerShell. MFA and the Exchange Online Remote PowerShell Module don't work with delegated authentication.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="17683-116">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="17683-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="17683-117">Предполагаемое время для завершения: 5 минут.</span><span class="sxs-lookup"><span data-stu-id="17683-117">Estimated time to complete: 5 minutes</span></span>

- <span data-ttu-id="17683-118">Ниже приведены версии Windows, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="17683-118">You can use the following versions of Windows:</span></span>
    
  - <span data-ttu-id="17683-119">Windows 10</span><span class="sxs-lookup"><span data-stu-id="17683-119">Windows 10</span></span>

  - <span data-ttu-id="17683-120">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="17683-120">Windows 8.1</span></span>

  - <span data-ttu-id="17683-121">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="17683-121">Windows Server 2016</span></span>

  - <span data-ttu-id="17683-122">Windows Server 2012 или Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="17683-122">Windows Server 2012 or Windows Server 2012 R2</span></span>

  - <span data-ttu-id="17683-123">Windows 7 с пакетом обновления 1 (SP1)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="17683-123">Windows 7 Service Pack 1 (SP1)<sup>\*</sup></span></span>

  - <span data-ttu-id="17683-124">Windows Server 2008 R2 с пакетом обновления 1 (SP1)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="17683-124">Windows Server 2008 R2 SP1<sup>\*</sup></span></span>

    <span data-ttu-id="17683-p105"><sup>\*</sup> Для более ранних версий Windows нужно установить Microsoft.NET Framework 4.5 или более поздней версии, а затем обновленную версию Windows Management Framework 3.0, 4.0 или 5.1 (только одну). Дополнительные сведения см. в статьях [Установка .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868), [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757), [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344) и [Windows Management Framework 5.1](https://aka.ms/wmf5download).</span><span class="sxs-lookup"><span data-stu-id="17683-p105"><sup>\*</sup> For older versions of Windows, you need to install the Microsoft.NET Framework 4.5 or later and then an updated version of the Windows Management Framework: 3.0, 4.0, or 5.1 (only one). For more information, see [Installing the .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868), [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757), [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344), and [Windows Management Framework 5.1](https://aka.ms/wmf5download).</span></span>

- <span data-ttu-id="17683-p106">Чтобы запускать сценарии, необходимо настроить Windows PowerShell. По умолчанию это приложение не настроено. При попытке подключения появится указанная ниже ошибка.</span><span class="sxs-lookup"><span data-stu-id="17683-p106">Windows PowerShell needs to be configured to run scripts, and by default, it isn't. You'll get the following error when you try to connect:</span></span>

  `Files cannot be loaded because running scripts is disabled on this system. Provide a valid certificate with which to sign the files.`

  <span data-ttu-id="17683-129">Чтобы требовать подпись надежного издателя для всех сценариев PowerShell, загружаемых из Интернета, выполните следующую команду в окне Windows PowerShell с повышенными привилегиями (окно Windows PowerShell, которое открывается с помощью параметра **Запуск от имени администратора**).</span><span class="sxs-lookup"><span data-stu-id="17683-129">To require all PowerShell scripts that you download from the internet are signed by a trusted publisher, run the following command in an elevated Windows PowerShell window (a Windows PowerShell window you open by selecting **Run as administrator**):</span></span>

    ```
    Set-ExecutionPolicy RemoteSigned
    ```

  <span data-ttu-id="17683-130">Достаточно настроить этот параметр один раз, и вам не придется делать это при каждом подключении.</span><span class="sxs-lookup"><span data-stu-id="17683-130">You need to configure this setting only once on your computer, not every time you connect.</span></span>

- <span data-ttu-id="17683-131">Сведения о сочетаниях клавиш, которые можно использовать в процедурах из этой статьи, см. в статье [Сочетания клавиш в Центре администрирования Exchange](https://go.microsoft.com/fwlink/p/?LinkId=534017).</span><span class="sxs-lookup"><span data-stu-id="17683-131">For information about keyboard shortcuts that might apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center](https://go.microsoft.com/fwlink/p/?LinkId=534017).</span></span>

## <a name="connect-to-exchange-online-for-customer-organizations"></a><span data-ttu-id="17683-132">Подключение к Exchange Online для организаций пользователей</span><span class="sxs-lookup"><span data-stu-id="17683-132">Connect to Exchange Online for customer organizations</span></span>

1. <span data-ttu-id="17683-133">На локальном компьютере откройте Windows PowerShell и запустите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="17683-133">On your local computer, open Windows PowerShell and run the following command.</span></span>
    
    ```
    $UserCredential = Get-Credential
    ```

    <span data-ttu-id="17683-134">В диалоговом окне **Запрос учетных данных Windows PowerShell** введите имя пользователя и пароль администратора DAP, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="17683-134">In the **Windows PowerShell Credential Request** dialog box, enter your DAP administrator user name and password, and then click **OK**.</span></span>
    
2. <span data-ttu-id="17683-135">Замените _\<customer tenant domain name\>_ именем домена клиента, к которому вы хотите подключиться, и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="17683-135">Replace _\<customer tenant domain name\>_ with the name of the tenant domain that you want to connect to, and run the following command:</span></span>
    
    ```
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid?DelegatedOrg=<customer tenant domain name> -Credential $UserCredential -Authentication Basic -AllowRedirection
    ```

    <span data-ttu-id="17683-136">Ключевой этап этой команды  указание пользователя, отчетные данные о котором нужно получить.</span><span class="sxs-lookup"><span data-stu-id="17683-136">The key step in this command is specifying which customer to access for the reporting information.</span></span> <span data-ttu-id="17683-137">Это можно сделать в параметре  _ConnectionURI_ , где указать полное доменное имя начального доменного имени в качестве значения `?DelegatedOrg=` .</span><span class="sxs-lookup"><span data-stu-id="17683-137">You do this in the  _ConnectionURI_ parameter, where you provide the FQDN of the initial domain name as the value for `?DelegatedOrg=`.</span></span> <span data-ttu-id="17683-138">Это значение указывает правильную конечную точку Exchange Online PowerShell для подключения.</span><span class="sxs-lookup"><span data-stu-id="17683-138">This value indicates the correct Exchange Online PowerShell endpoint to connect to.</span></span> <span data-ttu-id="17683-139">Удаленная оболочка PowerShell должна подключаться к Microsoft 365 Reports в контексте определенного клиента при каждом запуске отчета.</span><span class="sxs-lookup"><span data-stu-id="17683-139">Remote PowerShell must connect to Microsoft 365 reporting in the context of a specific customer each time a report is run.</span></span> <span data-ttu-id="17683-140">После подключения к Exchange Online PowerShell все последующие команды выполняются в контексте клиента, который предоставляет доступ ко всем доступным отчетам для клиента.</span><span class="sxs-lookup"><span data-stu-id="17683-140">After you connect to Exchange Online PowerShell, all subsequent commands are run in the context of the customer, which gives you access to all of the available reports for the customer.</span></span>
    
3. <span data-ttu-id="17683-141">Выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="17683-141">Run the following command.</span></span>
    
    ```
    Import-PSSession $Session
    ```

> [!NOTE]
> <span data-ttu-id="17683-p108">В одной учетной записи можно одновременно запускать до трех сеансов. По завершении настройки отключите удаленный сеанс PowerShell. Если закрыть окно Windows PowerShell, не выполнив отключение сеанса, то можно исчерпать лимит доступных сеансов удаленной среды PowerShell. К тому же, придется дождаться завершения сеанса. Чтобы отключить удаленный сеанс PowerShell, выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="17683-p108">There's a limit of three simultaneous sessions that can run under one account. Be sure to disconnect the remote PowerShell session when you're finished. If you close the Windows PowerShell window without disconnecting the session, you can use up all the remote PowerShell sessions available to you, and you'll need to wait for the sessions to expire. To disconnect the remote PowerShell session, run the following command:</span></span>

```
Remove-PSSession $Session
```
  
## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="17683-146">Как проверить, что все получилось?</span><span class="sxs-lookup"><span data-stu-id="17683-146">How do you know this worked?</span></span>

<span data-ttu-id="17683-p109">После шага 3 командлеты Exchange Online импортируются в локальный сеанс Windows PowerShell, на что указывает индикатор выполнения. Если при этом не возникают ошибки, подключение установлено. Чтобы выполнить быструю проверку, запустите командлет Exchange Online (например, **Get-Mailbox**) и просмотрите результаты его выполнения.</span><span class="sxs-lookup"><span data-stu-id="17683-p109">After Step 3, the Exchange Online cmdlets are imported into your local Windows PowerShell session as tracked by a progress bar. If you don't receive any errors, you connected successfully. A quick test is to run an Exchange Online cmdlet (for example, **Get-Mailbox**) and see the results.</span></span>
  
<span data-ttu-id="17683-150">Если возникают ошибки, просмотрите список возможных причин ниже.</span><span class="sxs-lookup"><span data-stu-id="17683-150">If you receive errors, check the following requirements:</span></span>
  
- <span data-ttu-id="17683-p110">Распространенная проблема — неправильный пароль. Еще раз повторите три описанные выше действия, уделив особое внимание действию 1 — вводу имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="17683-p110">A common problem is an incorrect password. Run the three steps again and pay close attention to the user name and password you enter in Step 1.</span></span>
    
- <span data-ttu-id="17683-p111">Для учетной записи, которую вы используете для подключения к Exchange Online, необходимо включить доступ к удаленному сеансу PowerShell. Дополнительные сведения см. в статье [Включение и отключение доступа к Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534018).</span><span class="sxs-lookup"><span data-stu-id="17683-p111">The account you use to connect to Exchange Online must be enabled for remote PowerShell. For more information, see [Enable or disable access to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534018).</span></span>
    
- <span data-ttu-id="17683-p112">Между клиентским компьютером и службой Exchange Online должен быть открыт порт TCP-порт 80. Вполне вероятно, что он уже открыт, но в этом следует убедиться, если в вашей организации действует политика ограниченного доступа к Интернету.</span><span class="sxs-lookup"><span data-stu-id="17683-p112">TCP port 80 traffic needs to be open between your local computer and Exchange Online. It's probably open, but it's something to consider if your organization has a restrictive Internet access policy.</span></span>
    
## <a name="call-the-cmdlet-directly-with-invoke-command"></a><span data-ttu-id="17683-157">Вызов командлета напрямую с помощью команды Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="17683-157">Call the cmdlet directly with Invoke-Command</span></span>

<span data-ttu-id="17683-p113">Импорт удаленного сеанса PowerShell (шаг 3) может занимать много времени, поскольку в нем используются _все_ командлеты Exchange Online. Это может быть проблемой при пакетной обработке (например, если создаются отчеты или выполняется пакетное изменение для разных клиентов). Вместо того чтобы использовать **Import-PSSession**, вы можете вызывать нужные командлеты напрямую с помощью команды **Invoke-Command**. Например, чтобы вызвать командлет **Get-Milbox**, вставьте этот код вместо команды `Import-PSSession $Session` на шаге 3:</span><span class="sxs-lookup"><span data-stu-id="17683-p113">Importing a remote PowerShell session (Step 3) can be a lengthy process because it brings in _all_ Exchange Online cmdlets. This can be an issue in batch processing (for example, when you're running reports or making bulk changes for different tenants). As an alternative to using **Import-PSSession**, you can call cmdlets you want to use directly with **Invoke-Command**. For example, to call the **Get-Milbox** cmdlet, substitute this syntax for the `Import-PSSession $Session` command in Step 3:</span></span>
  
```
Invoke-Command -Session $Session -ScriptBlock {Get-Mailbox}
```

## <a name="more-reporting-cmdlets"></a><span data-ttu-id="17683-162">Дополнительные командлеты для отчетов</span><span class="sxs-lookup"><span data-stu-id="17683-162">More reporting cmdlets</span></span>

<span data-ttu-id="17683-p114">В этом разделе используются командлеты Windows PowerShell. Дополнительные сведения об этих командлетах см. в следующих статьях.</span><span class="sxs-lookup"><span data-stu-id="17683-p114">The cmdlets that you used in this topic are Windows PowerShell cmdlets. For more information about these cmdlets, see the following topics:</span></span>
  
- <span data-ttu-id="17683-165">[Get-Credential](https://go.microsoft.com/fwlink/p/?LinkId=389618);</span><span class="sxs-lookup"><span data-stu-id="17683-165">[Get-Credential](https://go.microsoft.com/fwlink/p/?LinkId=389618)</span></span>
    
- <span data-ttu-id="17683-166">[New-PSSession](https://go.microsoft.com/fwlink/p/?LinkId=389621);</span><span class="sxs-lookup"><span data-stu-id="17683-166">[New-PSSession](https://go.microsoft.com/fwlink/p/?LinkId=389621)</span></span>
    
- <span data-ttu-id="17683-167">[Import-PSSession](https://go.microsoft.com/fwlink/p/?LinkId=389619);</span><span class="sxs-lookup"><span data-stu-id="17683-167">[Import-PSSession](https://go.microsoft.com/fwlink/p/?LinkId=389619)</span></span>
    
- <span data-ttu-id="17683-168">[Remove-PSSession](https://go.microsoft.com/fwlink/p/?LinkId=389620);</span><span class="sxs-lookup"><span data-stu-id="17683-168">[Remove-PSSession](https://go.microsoft.com/fwlink/p/?LinkId=389620)</span></span>
    
- [<span data-ttu-id="17683-169">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="17683-169">Set-ExecutionPolicy</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=389623)
    

