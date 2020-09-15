---
title: Подключение ко всем службам Microsoft 365 с помощью единого окна PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/10/2020
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
description: Сводка. Подключение ко всем службам Microsoft 365 с помощью единого окна PowerShell.
ms.openlocfilehash: e4cb3a10d14f6d4c16ef9323d6e5b3c500ebc0c5
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "47545978"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a><span data-ttu-id="33fac-103">Подключение ко всем службам Microsoft 365 с помощью единого окна PowerShell</span><span class="sxs-lookup"><span data-stu-id="33fac-103">Connect to all Microsoft 365 services in a single PowerShell window</span></span>

<span data-ttu-id="33fac-104">При использовании PowerShell для управления Microsoft 365 можно одновременно открывать различные сеансы PowerShell в разных окнах PowerShell, соответствующих задачам управления учетными записями пользователей, SharePoint Online, Exchange Online, Skype для бизнеса Online, Microsoft Teams и Центру безопасности &amp; соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="33fac-104">When you use PowerShell to manage Microsoft 365, it is possible to have multiple PowerShell sessions open at the same time in different PowerShell windows corresponding to managing user accounts, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="33fac-105">Этот способ управления Microsoft 365 не назовешь удобным, поскольку в таком случае отсутствует возможность обмениваться данными между этими окнами для управления разными службами.</span><span class="sxs-lookup"><span data-stu-id="33fac-105">This is not optimal for managing Microsoft 365 because you can't exchange data among those windows for cross-service management.</span></span> <span data-ttu-id="33fac-106">В этой статье описывается, как использовать один экземпляр PowerShell, с помощью которого можно управлять учетными записями Microsoft 365, Skype для бизнеса Online, Exchange Online, SharePoint Online, Microsoft Teams и Центром безопасности &amp; соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="33fac-106">This topic describes how to use a single instance of PowerShell from which you can manage Microsoft 365 accounts, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span>

>[!Note]
><span data-ttu-id="33fac-107">В этой статье приведены только команды для подключения к всемирному (+ GCC) облаку.</span><span class="sxs-lookup"><span data-stu-id="33fac-107">This article currently only contains the commands to connect to the Worldwide (+GCC) cloud.</span></span> <span data-ttu-id="33fac-108">Примечания содержат ссылки на статьи с информацией о подключении к другим облакам Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="33fac-108">Notes provide links to articles with information about connecting to the other Microsoft 365 clouds.</span></span>
>

## <a name="before-you-begin"></a><span data-ttu-id="33fac-109">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="33fac-109">Before you begin</span></span>

<span data-ttu-id="33fac-110">Существует ряд необходимых условий, которые нужно выполнить, прежде чем приступать к управлению всеми службами Microsoft 365 с помощью единого экземпляра PowerShell:</span><span class="sxs-lookup"><span data-stu-id="33fac-110">Before you can manage all of Microsoft 365 from a single instance of PowerShell, consider the following prerequisites:</span></span>
  
- <span data-ttu-id="33fac-111">Рабочая или учебная учетная запись Microsoft 365, которую вы используете для выполнения этих действий, должна входить в роль администратора Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="33fac-111">The Microsoft 365 work or school account that you use for these procedures needs to be a member of a Microsoft 365 admin role.</span></span> <span data-ttu-id="33fac-112">Дополнительные сведения см. в статье [О ролях администраторов](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="33fac-112">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span> <span data-ttu-id="33fac-113">Это требование для PowerShell для Microsoft 365, но не обязательно для других служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="33fac-113">This a requirement for PowerShell for Microsoft 365, not necessarily for all other Microsoft 365 services.</span></span>
    
- <span data-ttu-id="33fac-114">Ниже приведены 64-разрядные версии Windows, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="33fac-114">You can use the following 64-bit versions of Windows:</span></span>
    
  - <span data-ttu-id="33fac-115">Windows 10;</span><span class="sxs-lookup"><span data-stu-id="33fac-115">Windows 10</span></span>
    
  - <span data-ttu-id="33fac-116">Windows 8.1 или Windows 8</span><span class="sxs-lookup"><span data-stu-id="33fac-116">Windows 8.1 or Windows 8</span></span>
    
  - <span data-ttu-id="33fac-117">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="33fac-117">Windows Server 2019</span></span>
    
  - <span data-ttu-id="33fac-118">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="33fac-118">Windows Server 2016</span></span>
    
  - <span data-ttu-id="33fac-119">Windows Server 2012 R2 или Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="33fac-119">Windows Server 2012 R2 or Windows Server 2012</span></span>
    
  - <span data-ttu-id="33fac-120">Windows 7 с пакетом обновления 1 (SP1)\*</span><span class="sxs-lookup"><span data-stu-id="33fac-120">Windows 7 Service Pack 1 (SP1)\*</span></span>
    
  - <span data-ttu-id="33fac-121">Windows Server 2008 R2 с пакетом обновления 1 (SP1)\*</span><span class="sxs-lookup"><span data-stu-id="33fac-121">Windows Server 2008 R2 SP1\*</span></span>
    
    <span data-ttu-id="33fac-122">\* Необходимо установить Microsoft .NET Framework 4.5.*x*, а затем — Windows Management Framework 3.0 или Windows Management Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="33fac-122">\* You need to install the Microsoft .NET Framework 4.5.*x* and then either the Windows Management Framework 3.0 or the Windows Management Framework 4.0.</span></span> <span data-ttu-id="33fac-123">Подробнее см. [Установка .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868), [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) или[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344).</span><span class="sxs-lookup"><span data-stu-id="33fac-123">For more information, see [Installing the .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868) and [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) or [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344).</span></span>
    
    <span data-ttu-id="33fac-124">Необходимо использовать именно 64-разрядную версию Windows, поскольку это обязательное требование для модуля Skype для бизнеса Online и одного из модулей Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="33fac-124">You need to use a 64-bit version of Windows because of the requirements for the Skype for Business Online module and one of the Microsoft 365 modules.</span></span>
    
- <span data-ttu-id="33fac-125">Необходимо установить модули, необходимые для Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype для бизнеса Online и Teams:</span><span class="sxs-lookup"><span data-stu-id="33fac-125">You need to install the modules that are required for Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online and Teams:</span></span>
    
  - [<span data-ttu-id="33fac-126">Azure Active Directory V2</span><span class="sxs-lookup"><span data-stu-id="33fac-126">Azure Active Directory V2</span></span>](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  - [<span data-ttu-id="33fac-127">Командная консоль SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="33fac-127">SharePoint Online Management Shell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=255251)
  - [<span data-ttu-id="33fac-128">Skype для бизнеса Online, модуль PowerShell</span><span class="sxs-lookup"><span data-stu-id="33fac-128">Skype for Business Online, PowerShell Module</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=532439)
  - [<span data-ttu-id="33fac-129">Exchange Online PowerShell V2</span><span class="sxs-lookup"><span data-stu-id="33fac-129">Exchange Online PowerShell V2</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-v2-module)
  - [<span data-ttu-id="33fac-130">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="33fac-130">Teams PowerShell Overview</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  <span data-ttu-id="33fac-131">Необходимо настроить PowerShell для выполнения подписанных сценариев Skype для бизнеса Online и Центра безопасности &amp; соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="33fac-131">PowerShell needs to be configured to run signed scripts for Skype for Business Online and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="33fac-132">Для этого выполните следующую команду в сеансе PowerShell с повышенными привилегиями (открыв окно PowerShell с помощью команды **Запуск от имени администратора**).</span><span class="sxs-lookup"><span data-stu-id="33fac-132">To do this, run the following command in an elevated PowerShell session (a PowerShell window you open by selecting **Run as administrator**).</span></span>
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="exchange-online-and-security-amp-compliance-center-with-the-exchange-online-powershell-v2-module"></a><span data-ttu-id="33fac-133">Использование Exchange Online и Центра безопасности &amp; соответствия требованиям вместе с модулем Exchange Online PowerShell V2</span><span class="sxs-lookup"><span data-stu-id="33fac-133">Exchange Online and Security &amp; Compliance Center with the Exchange Online PowerShell V2 module</span></span>

<span data-ttu-id="33fac-134">В этой статье рассказывается, как использовать модуль Exchange Online PowerShell V2 для подключения к Exchange Online и Центру безопасности &amp; соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="33fac-134">This article uses the Exchange Online PowerShell V2 module to connect to both Exchange Online and Security &amp; Compliance Center.</span></span> <span data-ttu-id="33fac-135">Однако в настоящее время вы не можете подключиться к Exchange Online и к Центру безопасности &amp; соответствия требованиям **в одном и том же окне PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="33fac-135">However, at this time you cannot connect to both Exchange Online and the Security &amp; Compliance Center **in the same PowerShell window**.</span></span>

<span data-ttu-id="33fac-136">Таким образом, необходимо выбрать подключение к Exchange Online *или* к Центру безопасности &amp; соответствия требованиям при настройке окна PowerShell для нескольких служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="33fac-136">Therefore, you must choose a connection with either Exchange Online *or* the Security &amp; Compliance Center when configuring a PowerShell window for multiple Microsoft 365 services.</span></span>

## <a name="connection-steps-when-using-just-a-password"></a><span data-ttu-id="33fac-137">Этапы подключения только с использованием пароля</span><span class="sxs-lookup"><span data-stu-id="33fac-137">Connection steps when using just a password</span></span>

<span data-ttu-id="33fac-138">Ниже описаны действия, которые необходимо выполнить для подключения ко всем службам в одном окне PowerShell, если вы используете только пароль для входа в систему.</span><span class="sxs-lookup"><span data-stu-id="33fac-138">Here are the steps to connect to all the services in a single PowerShell window when you are using just a password for sign-in.</span></span>
  
1. <span data-ttu-id="33fac-139">Откройте Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="33fac-139">Open Windows PowerShell.</span></span>
    
2. <span data-ttu-id="33fac-140">Выполните эту команду и введите свои учетные данные Microsoft 365 для рабочей или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="33fac-140">Run this command and enter your Microsoft 365 work or school account credentials.</span></span>
    
   ```powershell
   $credential = Get-Credential
   ```

3. <span data-ttu-id="33fac-141">Выполните эту команду для подключения к Azure AD с помощью модуля Azure Active Directory PowerShell для Graph.</span><span class="sxs-lookup"><span data-stu-id="33fac-141">Run this command to connect to Azure AD using the Azure Active Directory PowerShell for Graph module.</span></span>
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   <span data-ttu-id="33fac-142">Или же, если вы используете модуль Microsoft Azure Active Directory для Windows PowerShell, выполните эту команду.</span><span class="sxs-lookup"><span data-stu-id="33fac-142">Alternately, if you are using the Microsoft Azure Active Directory Module for Windows PowerShell module, run this command.</span></span>
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > <span data-ttu-id="33fac-143">В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты с компонентом **Msol** в имени.</span><span class="sxs-lookup"><span data-stu-id="33fac-143">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="33fac-144">Чтобы использовать эти командлеты, необходимо запустить их из PowerShell.</span><span class="sxs-lookup"><span data-stu-id="33fac-144">To continue using these cmdlets, you must run them from PowerShell.</span></span>

4. <span data-ttu-id="33fac-145">Выполните приведенные ниже команды для подключения к SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="33fac-145">Run these commands to connect to SharePoint Online.</span></span> <span data-ttu-id="33fac-146">Введите название организации для вашего домена.</span><span class="sxs-lookup"><span data-stu-id="33fac-146">Specify the organization name for your domain.</span></span> <span data-ttu-id="33fac-147">Например, для "litwareinc.onmicrosoft.com", значение названия организации — "litwareinc".</span><span class="sxs-lookup"><span data-stu-id="33fac-147">For example, for "litwareinc.onmicrosoft.com", the  organization name value is "litwareinc".</span></span>
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $userCredential
   ```

5. <span data-ttu-id="33fac-148">Выполните следующие команды ля подключения к Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="33fac-148">Run these commands to connect to Skype for Business Online.</span></span> <span data-ttu-id="33fac-149">При первом подключении появится предупреждение об увеличении значения параметра `WSMan NetworkDelayms`. Можно смело пропустить это предупреждение.</span><span class="sxs-lookup"><span data-stu-id="33fac-149">A warning about increasing the `WSMan NetworkDelayms` value is expected the first time you connect and should be ignored.</span></span>
     
   ```powershell
   Import-Module SkypeOnlineConnector
   $sfboSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfboSession
   ```

6. <span data-ttu-id="33fac-150">Выполните эту команду для подключения к Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="33fac-150">Run this command to connect to Exchange Online.</span></span>
    
   ```powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -Credential $credential -ShowProgress $true
   ```

   > [!Note]
   > <span data-ttu-id="33fac-151">Чтобы подключиться к Exchange Online для облаков Microsoft 365, отличных от всемирного облака, см. статью [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="33fac-151">To connect to Exchange Online for Microsoft 365 clouds other than Worldwide, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

7. <span data-ttu-id="33fac-152">Поочередно выполните следующие команды для подключения к Центру безопасности &amp; соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="33fac-152">Alternately, run these commands to connect to the Security &amp; Compliance Center.</span></span>
    
   ```powershell
   $acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
   Import-Module ExchangeOnlineManagement
   Connect-IPPSSession -UserPrincipalName $acctName
   ```

   > [!Note]
   > <span data-ttu-id="33fac-153">Чтобы подключиться к Центру безопасности&amp; соответствия требованиям для облаков Microsoft 365, отличных от всемирного облака, см. статью [Подключение к Центру безопасности и соответствия требованиям PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="33fac-153">To connect to the Security &amp; Compliance Center for Microsoft 365 clouds other than Worldwide, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

8. <span data-ttu-id="33fac-154">Выполните следующие команды для подключения к Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="33fac-154">Run these commands to connect to Teams PowerShell.</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > <span data-ttu-id="33fac-155">Чтобы подключиться к облакам Microsoft Teams, отличным от всемирного облака, см. раздел [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams).</span><span class="sxs-lookup"><span data-stu-id="33fac-155">To connect to Microsoft Teams clouds other than Worldwide, see [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams).</span></span>


### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="33fac-156">Использование модуля Azure Active Directory PowerShell для Graph</span><span class="sxs-lookup"><span data-stu-id="33fac-156">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="33fac-157">Ниже, в едином текстовом блоке перечислены команды для всех служб, *за исключением Центра безопасности &amp; соответствия требованиям,* при использовании модуля Azure Active Directory для Graph.</span><span class="sxs-lookup"><span data-stu-id="33fac-157">Here are the commands for all of the services *except Security &amp; Compliance Center* in a single block when using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="33fac-158">Укажите доменное имя узла, а затем запустите их одновременно.</span><span class="sxs-lookup"><span data-stu-id="33fac-158">Specify the name of your domain host, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="33fac-159">Ниже, в едином текстовом блоке перечислены команды для всех служб, *за исключением Exchange Online,* при использовании модуля Azure Active Directory PowerShell для Graph.</span><span class="sxs-lookup"><span data-stu-id="33fac-159">Here are the commands for all of the services *except Exchange Online* in a single block when using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="33fac-160">Укажите доменное имя узла и UPN для входа, а затем запустите их одновременно.</span><span class="sxs-lookup"><span data-stu-id="33fac-160">Specify the name of your domain host and the UPN for the sign-in, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="33fac-161">Модуль Microsoft Azure Active Directory для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="33fac-161">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="33fac-162">Ниже, в едином текстовом блоке перечислены команды для всех служб, *за исключением Центра безопасности &amp; соответствия требованиям,* при использовании модуля Microsoft Azure Active Directory для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="33fac-162">Here are the commands for all of the services *except Security &amp; Compliance Center* in a single block when using the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="33fac-163">Укажите доменное имя узла, а затем запустите их одновременно.</span><span class="sxs-lookup"><span data-stu-id="33fac-163">Specify the name of your domain host, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-MsolService -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="33fac-164">Ниже, в едином текстовом блоке перечислены команды для всех служб, *за исключением Exchange Online,* при использовании модуля Microsoft Azure Active Directory для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="33fac-164">Here are the commands for all of the services *except Exchange Online* in a single block when using the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="33fac-165">Укажите доменное имя узла и UPN для входа, а затем запустите их одновременно.</span><span class="sxs-lookup"><span data-stu-id="33fac-165">Specify the name of your domain host and the UPN for the sign-in, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```
## <a name="connection-steps-when-using-multi-factor-authentication"></a><span data-ttu-id="33fac-166">Этапы подключения при использовании многофакторной идентификации</span><span class="sxs-lookup"><span data-stu-id="33fac-166">Connection steps when using multi-factor authentication</span></span>

### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="33fac-167">Использование модуля Azure Active Directory PowerShell для Graph</span><span class="sxs-lookup"><span data-stu-id="33fac-167">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="33fac-168">Ниже, в едином текстовом блоке перечислены все команды, которые можно использовать для подключения к нескольким службам Microsoft 365, *за исключением Центра безопасности &amp; соответствия требованиям,* с помощью многофакторной идентификации и при использовании модуля Azure Active Directory PowerShell для Graph.</span><span class="sxs-lookup"><span data-stu-id="33fac-168">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Security &amp; Compliance Center* with multi-factor authentication using the Azure Active Directory PowerShell for Graph module.</span></span>

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
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
<span data-ttu-id="33fac-169">Ниже в едином текстовом блоке перечислены все команды, которые можно использовать для подключения к нескольким службам Microsoft 365, *за исключением Exchange Online,* с помощью многофакторной идентификации и при использовании модуля Azure Active Directory PowerShell для Graph.</span><span class="sxs-lookup"><span data-stu-id="33fac-169">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Exchange Online* with multi-factor authentication using the Azure Active Directory PowerShell for Graph module.</span></span>

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
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="33fac-170">Модуль Microsoft Azure Active Directory для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="33fac-170">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="33fac-171">Ниже, в едином текстовом блоке перечислены все команды, которые можно использовать для подключения к нескольким службам Microsoft 365, *за исключением Центра безопасности &amp; соответствия требованиям,* с помощью многофакторной идентификации и при использовании модуля Microsoft Azure Active Directory для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="33fac-171">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Security &amp; Compliance Center* with multi-factor authentication using the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

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
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
<span data-ttu-id="33fac-172">Ниже, в едином текстовом блоке перечислены все команды, которые можно использовать для подключения к нескольким службам Microsoft 365, *за исключением Exchange Online,* с помощью многофакторной идентификации и при использовании модуля Microsoft Azure Active Directory для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="33fac-172">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Exchange Online* using multi-factor authentication with the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

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
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

## <a name="close-the-powershell-window"></a><span data-ttu-id="33fac-173">Закрыть окно PowerShell</span><span class="sxs-lookup"><span data-stu-id="33fac-173">Close the PowerShell window</span></span>

<span data-ttu-id="33fac-174">Когда вы будете готовы закрыть окно PowerShell, выполните эту команду, чтобы завершить все активные сессии в Skype для бизнеса Online, SharePoint, а также в Teams:</span><span class="sxs-lookup"><span data-stu-id="33fac-174">When you are ready to close down the PowerShell window, run this command to remove the active sessions to Skype for Business Online, SharePoint Online, and Teams:</span></span>
  
```powershell
Remove-PSSession $sfboSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```


## <a name="see-also"></a><span data-ttu-id="33fac-175">См. также</span><span class="sxs-lookup"><span data-stu-id="33fac-175">See also</span></span>

- [<span data-ttu-id="33fac-176">Подключение к Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="33fac-176">Connect to Microsoft 365 with PowerShell</span></span>](connect-to-microsoft-365-powershell.md)
- [<span data-ttu-id="33fac-177">Управление SharePoint Online с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="33fac-177">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [<span data-ttu-id="33fac-178">Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="33fac-178">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
