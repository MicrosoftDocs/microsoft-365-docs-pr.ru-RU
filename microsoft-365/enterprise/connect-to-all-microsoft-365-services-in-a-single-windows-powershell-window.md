---
title: Подключение ко всем службам Microsoft 365 с помощью единого окна Windows PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- Ent_Office_Other
- O365ITProTrain
- httpsfix
ms.assetid: 53d3eef6-4a16-4fb9-903c-816d5d98d7e8
description: 'Сводка: Подключение ко всем службам Microsoft 365 с помощью единого окна Windows PowerShell'
ms.openlocfilehash: d4e4bf6ec07ee4a0a5b2f8cb1c83ffacd221eaa0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693312"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window"></a><span data-ttu-id="d21fd-103">Подключение ко всем службам Microsoft 365 с помощью единого окна Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d21fd-103">Connect to all Microsoft 365 services in a single Windows PowerShell window</span></span>

<span data-ttu-id="d21fd-104">При использовании PowerShell для управления Microsoft 365 можно открывать до пяти различных сеансов Windows PowerShell одновременно, соответствующих центру администрирования Microsoft 365, SharePoint Online, Exchange Online, Skype для бизнеса Online, Microsoft Teams и Центру безопасности &amp; соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="d21fd-104">When you use PowerShell to manage Microsoft 365, it is possible to have up to five different Windows PowerShell sessions open at the same time corresponding to Microsoft 365 admin center, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="d21fd-105">Если подключаться в отдельные сеансы Windows PowerShell пятью различными способами, ваш рабочий стол будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d21fd-105">With five different connection methods in separate Windows PowerShell sessions, your desktop could look like this:</span></span>
  
![Пять консолей Windows PowerShell, работающих одновременно](../media/a1a852c2-89ea-4e8e-8d8b-dcdf596763d1.png)
  
<span data-ttu-id="d21fd-107">Этот способ управления Microsoft 365 не назовешь удобным, поскольку в таком случае отсутствует возможность обмениваться данными между этими пяти окнами для управления разными службами.</span><span class="sxs-lookup"><span data-stu-id="d21fd-107">This is not optimal for managing Microsoft 365 because you can't exchange data among those five windows for cross-service management.</span></span> <span data-ttu-id="d21fd-108">В этой статье описывается, как использовать один экземпляр Windows PowerShell, с помощью которого можно управлять учетными записями Microsoft 365, Skype для бизнеса Online, Exchange Online, SharePoint Online, Microsoft Teams и Центром безопасности &amp; соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="d21fd-108">This topic describes how to use a single instance of Windows PowerShell from which you can manage Microsoft 365 accounts, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span>

>[!Note]
><span data-ttu-id="d21fd-109">В этой статье приведены только команды для подключения к всемирному (+ GCC) облаку.</span><span class="sxs-lookup"><span data-stu-id="d21fd-109">This article currently only contains the commands to connect to the Worldwide (+GCC) cloud.</span></span> <span data-ttu-id="d21fd-110">Дополнительные примечания содержат ссылки на статьи с информацией о подключении к другим облакам Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d21fd-110">Additional notes provide links to articles with information about connecting to the other Microsoft 365 clouds.</span></span>
>

## <a name="before-you-begin"></a><span data-ttu-id="d21fd-111">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="d21fd-111">Before you begin</span></span>

<span data-ttu-id="d21fd-112">Существует ряд необходимых условий, которые необходимо выполнить, прежде чем приступать к управлению всеми службами Microsoft 365 с помощью единого экземпляра Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d21fd-112">Before you can manage all of Microsoft 365 from a single instance of Windows PowerShell, consider the following prerequisites:</span></span>
  
- <span data-ttu-id="d21fd-113">Рабочая или учебная учетная запись Microsoft 365, которую вы используете для выполнения этих действий, должна входить в роль администратора Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d21fd-113">The Microsoft 365 work or school account that you use for these procedures needs to be a member of a Microsoft 365 admin role.</span></span> <span data-ttu-id="d21fd-114">Дополнительные сведения см. в статье [О ролях администраторов](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="d21fd-114">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide).</span></span> <span data-ttu-id="d21fd-115">Это требование для PowerShell для Microsoft 365, но не обязательно для других служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d21fd-115">This a requirement for PowerShell for Microsoft 365, not necessarily for all other Microsoft 365 services.</span></span>
    
- <span data-ttu-id="d21fd-116">Ниже приведены 64-разрядные версии Windows, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="d21fd-116">You can use the following 64-bit versions of Windows:</span></span>
    
  - <span data-ttu-id="d21fd-117">Windows 10;</span><span class="sxs-lookup"><span data-stu-id="d21fd-117">Windows 10</span></span>
    
  - <span data-ttu-id="d21fd-118">Windows 8.1 или Windows 8</span><span class="sxs-lookup"><span data-stu-id="d21fd-118">Windows 8.1 or Windows 8</span></span>
    
  - <span data-ttu-id="d21fd-119">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="d21fd-119">Windows Server 2019</span></span>
    
  - <span data-ttu-id="d21fd-120">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="d21fd-120">Windows Server 2016</span></span>
    
  - <span data-ttu-id="d21fd-121">Windows Server 2012 R2 или Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="d21fd-121">Windows Server 2012 R2 or Windows Server 2012</span></span>
    
  - <span data-ttu-id="d21fd-122">Windows 7 с пакетом обновления 1 (SP1)\*</span><span class="sxs-lookup"><span data-stu-id="d21fd-122">Windows 7 Service Pack 1 (SP1)\*</span></span>
    
  - <span data-ttu-id="d21fd-123">Windows Server 2008 R2 с пакетом обновления 1 (SP1)\*</span><span class="sxs-lookup"><span data-stu-id="d21fd-123">Windows Server 2008 R2 SP1\*</span></span>
    
    <span data-ttu-id="d21fd-124">\* Необходимо установить Microsoft .NET Framework 4.5.*x*, а затем — Windows Management Framework 3.0 или Windows Management Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="d21fd-124">\* You need to install the Microsoft .NET Framework 4.5.*x* and then either the Windows Management Framework 3.0 or the Windows Management Framework 4.0.</span></span> <span data-ttu-id="d21fd-125">Подробнее см. [Установка .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868), [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) или[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344).</span><span class="sxs-lookup"><span data-stu-id="d21fd-125">For more information, see [Installing the .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868) and [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) or [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344).</span></span>
    
    <span data-ttu-id="d21fd-126">Необходимо использовать именно 64-разрядную версию Windows, поскольку это обязательное требование для модуля Skype для бизнеса Online и одного из модулей Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d21fd-126">You need to use a 64-bit version of Windows because of the requirements for the Skype for Business Online module and one of the Microsoft 365 modules.</span></span>
    
- <span data-ttu-id="d21fd-127">Необходимо установить модули, необходимые для Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype для бизнеса Online и Teams:</span><span class="sxs-lookup"><span data-stu-id="d21fd-127">You need to install the modules that are required for Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online and Teams:</span></span>
    
   - [<span data-ttu-id="d21fd-128">Azure Active Directory V2</span><span class="sxs-lookup"><span data-stu-id="d21fd-128">Azure Active Directory V2</span></span>](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
   - [<span data-ttu-id="d21fd-129">Командная консоль SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d21fd-129">SharePoint Online Management Shell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=255251)
   - [<span data-ttu-id="d21fd-130">Skype для бизнеса Online, модуль Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d21fd-130">Skype for Business Online, Windows PowerShell Module</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=532439)
   - [<span data-ttu-id="d21fd-131">Exchange Online PowerShell V2</span><span class="sxs-lookup"><span data-stu-id="d21fd-131">Exchange Online PowerShell V2</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module)
   - [<span data-ttu-id="d21fd-132">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="d21fd-132">Teams PowerShell Overview</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  <span data-ttu-id="d21fd-133">Необходимо настроить Windows PowerShell для выполнения подписанных сценариев Skype для бизнеса Online и Центра безопасности &amp; соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="d21fd-133">Windows PowerShell needs to be configured to run signed scripts for Skype for Business Online and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="d21fd-134">Для этого выполните следующую команду в сеансе Windows PowerShell в окне с повышенными привилегиями (т. е. необходимо открыть окно Windows PowerShell с помощью команды **Запуск от имени администратора**).</span><span class="sxs-lookup"><span data-stu-id="d21fd-134">To do this, run the following command in an elevated Windows PowerShell session (a Windows PowerShell window you open by selecting **Run as administrator**).</span></span>
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="connection-steps-when-using-just-a-password"></a><span data-ttu-id="d21fd-135">Этапы подключения только с использованием пароля</span><span class="sxs-lookup"><span data-stu-id="d21fd-135">Connection steps when using just a password</span></span>

<span data-ttu-id="d21fd-136">Ниже описаны действия, которые необходимо выполнить для подключения ко всем службам в одном окне PowerShell, если вы используете только пароль для входа в систему.</span><span class="sxs-lookup"><span data-stu-id="d21fd-136">Here are the steps to connect to all the services in a single PowerShell window when you are using just a password for sign-in.</span></span>
  
1. <span data-ttu-id="d21fd-137">Откройте Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d21fd-137">Open Windows PowerShell.</span></span>
    
2. <span data-ttu-id="d21fd-138">Выполните эту команду и введите свои учетные данные Microsoft 365 для рабочей или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="d21fd-138">Run this command and enter your Microsoft 365 work or school account credentials.</span></span>
    
   ```powershell
   $credential = Get-Credential
   ```

3. <span data-ttu-id="d21fd-139">Выполните эту команду для подключения к Azure AD с помощью модуля Azure Active Directory PowerShell для Graph.</span><span class="sxs-lookup"><span data-stu-id="d21fd-139">Run this command to connect to Azure AD using the Azure Active Directory PowerShell for Graph module.</span></span>
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   <span data-ttu-id="d21fd-140">Или же, если вы используете модуль Microsoft Azure Active Directory для Windows PowerShell, выполните эту команду.</span><span class="sxs-lookup"><span data-stu-id="d21fd-140">Alternately, if you are using the Microsoft Azure Active Directory Module for Windows PowerShell module, run this command.</span></span>
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > <span data-ttu-id="d21fd-141">В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты с компонентом **Msol** в имени.</span><span class="sxs-lookup"><span data-stu-id="d21fd-141">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="d21fd-142">Чтобы использовать эти командлеты, необходимо запустить их из Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d21fd-142">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>

4. <span data-ttu-id="d21fd-143">Выполните приведенные ниже команды для подключения к SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="d21fd-143">Run these commands to connect to SharePoint Online.</span></span> <span data-ttu-id="d21fd-144">Введите название организации для вашего домена.</span><span class="sxs-lookup"><span data-stu-id="d21fd-144">Specify the organization name for your domain.</span></span> <span data-ttu-id="d21fd-145">Например, для "litwareinc.onmicrosoft.com", значение названия организации — "litwareinc".</span><span class="sxs-lookup"><span data-stu-id="d21fd-145">For example, for "litwareinc.onmicrosoft.com", the  organization name value is "litwareinc".</span></span>
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $userCredential
   ```

5. <span data-ttu-id="d21fd-146">Выполните следующие команды ля подключения к Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="d21fd-146">Run these commands to connect to Skype for Business Online.</span></span> <span data-ttu-id="d21fd-147">При первом подключении появится предупреждение об увеличении значения параметра `WSMan NetworkDelayms`. Можно смело пропустить это предупреждение.</span><span class="sxs-lookup"><span data-stu-id="d21fd-147">A warning about increasing the `WSMan NetworkDelayms` value is expected the first time you connect and should be ignored.</span></span>
     
   ```powershell
   Import-Module SkypeOnlineConnector
   $sfboSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfboSession
   ```

6. <span data-ttu-id="d21fd-148">Выполните эту команду для подключения к Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d21fd-148">Run this command to connect to Exchange Online.</span></span>
    
   ```powershell
   Connect-ExchangeOnline -Credential $credential -ShowProgress $true
   ```

   > [!Note]
   > <span data-ttu-id="d21fd-149">Чтобы подключиться к Exchange Online для не всемирных облаков Microsoft 365, используйте параметр **-ExchangeEnvironmentName**.</span><span class="sxs-lookup"><span data-stu-id="d21fd-149">To connect to Exchange Online for Microsoft 365 clouds other than Worldwide, use the **-ExchangeEnvironmentName** parameter.</span></span> <span data-ttu-id="d21fd-150">Дополнительные сведения см. в разделе[Connect-ExchangeOnline](https://docs.microsoft.com/powershell/module/exchange/powershell-v2-module/connect-exchangeonline?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="d21fd-150">See [Connect-ExchangeOnline](https://docs.microsoft.com/powershell/module/exchange/powershell-v2-module/connect-exchangeonline?view=exchange-ps) for more information.</span></span>

7. <span data-ttu-id="d21fd-151">Выполните следующие команды для подключения к Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d21fd-151">Run these commands to connect to Teams PowerShell.</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > <span data-ttu-id="d21fd-152">Чтобы подключиться к облакам Microsoft Teams, отличным от всемирного облака, см. раздел [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="d21fd-152">To connect to Microsoft Teams clouds other than Worldwide, see [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps).</span></span>

8. <span data-ttu-id="d21fd-153">Выполните следующие команды для подключения к Центру безопасности &amp; соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="d21fd-153">Run these commands to connect to the Security &amp; Compliance Center.</span></span>
    
   ```powershell
   $SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $credential -Authentication "Basic" -AllowRedirection
   Import-PSSession $SccSession -Prefix cc
   ```

   > [!Note]
   > <span data-ttu-id="d21fd-154">Чтобы подключиться к Центру безопасности&amp; соответствия требованиям для облаков Microsoft 365, отличных от всемирного облака, см. статью раздел [Подключение к Центру безопасности и соответствия требованиям PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="d21fd-154">To connect to the Security &amp; Compliance Center for Microsoft 365 clouds other than Worldwide, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

<span data-ttu-id="d21fd-155">Ниже в едином блоке перечислены все команды при использовании модуля Azure Active Directory PowerShell для Graph.</span><span class="sxs-lookup"><span data-stu-id="d21fd-155">Here are all the commands in a single block when using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="d21fd-156">Укажите доменное имя узла, а затем запустите их одновременно.</span><span class="sxs-lookup"><span data-stu-id="d21fd-156">Specify the name of your domain host, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
$SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $credential -Authentication "Basic" -AllowRedirection
Import-PSSession $SccSession -Prefix cc
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="d21fd-157">Или же, можно использовать перечисленные в едином блоке команды при использовании модуля Microsoft Azure Active Directory для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d21fd-157">Alternately, here are all the commands in a single block when using the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="d21fd-158">Укажите доменное имя узла, а затем запустите их одновременно.</span><span class="sxs-lookup"><span data-stu-id="d21fd-158">Specify the name of your domain host, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-MsolService -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
$SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $credential -Authentication "Basic" -AllowRedirection
Import-PSSession $SccSession -Prefix cc
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="d21fd-159">Когда вы будете готовы закрыть окно Windows PowerShell, выполните эту команду, чтобы удалить активные сеансы в Skype для бизнеса Online, SharePoint Online, Центре безопасности&amp; соответствия требованиям, а также в Teams.</span><span class="sxs-lookup"><span data-stu-id="d21fd-159">When you are ready to close down the Windows PowerShell window, run this command to remove the active sessions to Skype for Business Online, SharePoint Online, the Security &amp; Compliance Center, and Teams:</span></span>
  
```powershell
Remove-PSSession $sfboSession ; Remove-PSSession $SccSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```

## <a name="connection-steps-when-using-multi-factor-authentication"></a><span data-ttu-id="d21fd-160">Этапы подключения при использовании многофакторной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="d21fd-160">Connection steps when using multi-factor authentication</span></span>

<span data-ttu-id="d21fd-161">Ниже в едином блоке перечислены все команды для подключения к Azure AD, SharePoint Online, Skype для бизнеса, Exchange Online и Teams с использованием многофакторной проверки подлинности в одном окне с помощью модуля Azure Active Directory PowerShell для Graph.</span><span class="sxs-lookup"><span data-stu-id="d21fd-161">Here are all the commands in a single block to connect to Azure AD, SharePoint Online, Skype for Business, Exchange Online, and Teams using multi-factor authentication in a single window using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="d21fd-162">Укажите имя участника-пользователя (UPN) для учетной записи пользователя и доменное имя узла, а затем запустите их одновременно.</span><span class="sxs-lookup"><span data-stu-id="d21fd-162">Specify the user principal name (UPN) name of a user account and your domain host name, and then run them all at one time.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Exchange Online
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

<span data-ttu-id="d21fd-163">Или же, можно использовать перечисленные команды при использовании модуля Microsoft Azure Active Directory для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d21fd-163">Alternately, here are all the commands when using the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Exchange Online
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

<span data-ttu-id="d21fd-164">Сведения о подключении к Центру безопасности &amp; соответствия требованиям с использованием многофакторной проверки подлинности см. в разделе[Подключение к Центру безопасности и соответствия требованиям с использованием многофакторной проверки подлинности](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell?view=exchange-ps):</span><span class="sxs-lookup"><span data-stu-id="d21fd-164">For the Security &amp; Compliance Center, see [Connect to Security & Compliance Center PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell?view=exchange-ps) to connect using multi-factor authentication:</span></span>

## <a name="see-also"></a><span data-ttu-id="d21fd-165">См. также</span><span class="sxs-lookup"><span data-stu-id="d21fd-165">See also</span></span>

- [<span data-ttu-id="d21fd-166">Подключение к Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="d21fd-166">Connect to Microsoft 365 with PowerShell</span></span>](connect-to-microsoft-365-powershell.md)
- [<span data-ttu-id="d21fd-167">Управление SharePoint Online с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="d21fd-167">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [<span data-ttu-id="d21fd-168">Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="d21fd-168">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [<span data-ttu-id="d21fd-169">Использование Windows PowerShell для создания отчетов в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d21fd-169">Use Windows PowerShell to create reports in Microsoft 365</span></span>](use-windows-powershell-to-create-reports-in-microsoft-365.md)
