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
# <a name="connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated-access-permissions-dap-partners"></a>Подключение к клиентам Exchange Online с помощью удаленного сеанса Windows PowerShell для партнеров службы разрешений делегированного доступа (DAP)

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

> [!IMPORTANT]
> Процедуры, описанные в этой статье, предназначены только для партнеров службы разрешений делегированного доступа (DAP). Если вы не являетесь партнером DAP, не используйте эти процедуры. 
  
Партнеры DAP являются партнерами синдикации и поставщиков облачных решений (CSP). Они часто являются поставщиками сети или телекоммуникационных услуг в других компаниях. Они включают подписки в услуги для своих клиентов. Они владеют партнерской арендой, которая автоматически получает права администратора от имени (АОБО) для пользователей Microsoft 365, чтобы они могли администрировать и предоставлять отчеты для всех клиентов клиенты.

Партнеры по настройке доступа к данным могут использовать Exchange Online PowerShell для управления параметрами клиента Exchange Online и получения отчетов Microsoft 365 из командной строки. С помощью Windows PowerShell на локальном компьютере можно создать удаленный сеанс PowerShell с Exchange Online. Это простой процесс в три этапа, в котором вы вводите свои учетные данные, предоставляете необходимые параметры подключения, а затем импортируете командлеты Exchange Online в локальный сеанс Windows PowerShell, чтобы их можно было использовать.

> [!NOTE]
> Партнеры DAP не могут использовать процедуры, описанные в статье [Подключение к Exchange Online PowerShell с помощью многофакторной проверки подлинности](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell), чтобы подключаться к клиентским организациям пользователей в Exchange Online PowerShell. Многофакторная проверка подлинности и удаленный модуль PowerShell в Exchange Online не поддерживают делегированную проверку подлинности.
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Предполагаемое время для завершения: 5 минут.

- Ниже приведены версии Windows, которые можно использовать.
    
  - Windows 10

  - Windows 8.1

  - Windows Server 2016

  - Windows Server 2012 или Windows Server 2012 R2

  - Windows 7 с пакетом обновления 1 (SP1)<sup>*</sup>

  - Windows Server 2008 R2 с пакетом обновления 1 (SP1)<sup>*</sup>

    <sup>*</sup> Для более ранних версий Windows нужно установить Microsoft.NET Framework 4.5 или более поздней версии, а затем обновленную версию Windows Management Framework 3.0, 4.0 или 5.1 (только одну). Дополнительные сведения см. в статьях [Установка .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868), [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757), [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344) и [Windows Management Framework 5.1](https://aka.ms/wmf5download).

- Чтобы запускать сценарии, необходимо настроить Windows PowerShell. По умолчанию это приложение не настроено. При попытке подключения появится указанная ниже ошибка.

  `Files cannot be loaded because running scripts is disabled on this system. Provide a valid certificate with which to sign the files.`

  Чтобы требовать подпись надежного издателя для всех сценариев PowerShell, загружаемых из Интернета, выполните следующую команду в окне Windows PowerShell с повышенными привилегиями (окно Windows PowerShell, которое открывается с помощью параметра **Запуск от имени администратора**).

    ```
    Set-ExecutionPolicy RemoteSigned
    ```

  Достаточно настроить этот параметр один раз, и вам не придется делать это при каждом подключении.

- Сведения о сочетаниях клавиш, которые можно использовать в процедурах из этой статьи, см. в статье [Сочетания клавиш в Центре администрирования Exchange](https://go.microsoft.com/fwlink/p/?LinkId=534017).

## <a name="connect-to-exchange-online-for-customer-organizations"></a>Подключение к Exchange Online для организаций пользователей

1. На локальном компьютере откройте Windows PowerShell и запустите следующую команду.
    
    ```
    $UserCredential = Get-Credential
    ```

    В диалоговом окне **Запрос учетных данных Windows PowerShell** введите имя пользователя и пароль администратора DAP, а затем нажмите кнопку **ОК**.
    
2. Замените _\<customer tenant domain name\>_ именем домена клиента, к которому вы хотите подключиться, и выполните следующую команду:
    
    ```
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid?DelegatedOrg=<customer tenant domain name> -Credential $UserCredential -Authentication Basic -AllowRedirection
    ```

    Ключевой этап этой команды  указание пользователя, отчетные данные о котором нужно получить. Это можно сделать в параметре  _ConnectionURI_ , где указать полное доменное имя начального доменного имени в качестве значения `?DelegatedOrg=` . Это значение указывает правильную конечную точку Exchange Online PowerShell для подключения. Удаленная оболочка PowerShell должна подключаться к Microsoft 365 Reports в контексте определенного клиента при каждом запуске отчета. После подключения к Exchange Online PowerShell все последующие команды выполняются в контексте клиента, который предоставляет доступ ко всем доступным отчетам для клиента.
    
3. Выполните следующую команду.
    
    ```
    Import-PSSession $Session
    ```

> [!NOTE]
> В одной учетной записи можно одновременно запускать до трех сеансов. По завершении настройки отключите удаленный сеанс PowerShell. Если закрыть окно Windows PowerShell, не выполнив отключение сеанса, то можно исчерпать лимит доступных сеансов удаленной среды PowerShell. К тому же, придется дождаться завершения сеанса. Чтобы отключить удаленный сеанс PowerShell, выполните приведенную ниже команду.

```
Remove-PSSession $Session
```
  
## <a name="how-do-you-know-this-worked"></a>Как проверить, что все получилось?

После шага 3 командлеты Exchange Online импортируются в локальный сеанс Windows PowerShell, на что указывает индикатор выполнения. Если при этом не возникают ошибки, подключение установлено. Чтобы выполнить быструю проверку, запустите командлет Exchange Online (например, **Get-Mailbox**) и просмотрите результаты его выполнения.
  
Если возникают ошибки, просмотрите список возможных причин ниже.
  
- Распространенная проблема — неправильный пароль. Еще раз повторите три описанные выше действия, уделив особое внимание действию 1 — вводу имени пользователя и пароля.
    
- Для учетной записи, которую вы используете для подключения к Exchange Online, необходимо включить доступ к удаленному сеансу PowerShell. Дополнительные сведения см. в статье [Включение и отключение доступа к Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534018).
    
- Между клиентским компьютером и службой Exchange Online должен быть открыт порт TCP-порт 80. Вполне вероятно, что он уже открыт, но в этом следует убедиться, если в вашей организации действует политика ограниченного доступа к Интернету.
    
## <a name="call-the-cmdlet-directly-with-invoke-command"></a>Вызов командлета напрямую с помощью команды Invoke-Command

Импорт удаленного сеанса PowerShell (шаг 3) может занимать много времени, поскольку в нем используются _все_ командлеты Exchange Online. Это может быть проблемой при пакетной обработке (например, если создаются отчеты или выполняется пакетное изменение для разных клиентов). Вместо того чтобы использовать **Import-PSSession**, вы можете вызывать нужные командлеты напрямую с помощью команды **Invoke-Command**. Например, чтобы вызвать командлет **Get-Milbox**, вставьте этот код вместо команды `Import-PSSession $Session` на шаге 3:
  
```
Invoke-Command -Session $Session -ScriptBlock {Get-Mailbox}
```

## <a name="more-reporting-cmdlets"></a>Дополнительные командлеты для отчетов

В этом разделе используются командлеты Windows PowerShell. Дополнительные сведения об этих командлетах см. в следующих статьях.
  
- [Get-Credential](https://go.microsoft.com/fwlink/p/?LinkId=389618);
    
- [New-PSSession](https://go.microsoft.com/fwlink/p/?LinkId=389621);
    
- [Import-PSSession](https://go.microsoft.com/fwlink/p/?LinkId=389619);
    
- [Remove-PSSession](https://go.microsoft.com/fwlink/p/?LinkId=389620);
    
- [Set-ExecutionPolicy](https://go.microsoft.com/fwlink/p/?LinkId=389623)
    

