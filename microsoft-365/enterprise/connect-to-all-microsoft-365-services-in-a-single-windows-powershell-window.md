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
ms.openlocfilehash: 4266b4f216b4c9df48f0c19d1d2123269eb32cae
ms.sourcegitcommit: 00d231bf0100e843a5a93161695e87ceff9e1349
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/13/2021
ms.locfileid: "49849597"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a><span data-ttu-id="db6c7-103">Подключение ко всем службам Microsoft 365 с помощью единого окна PowerShell</span><span class="sxs-lookup"><span data-stu-id="db6c7-103">Connect to all Microsoft 365 services in a single PowerShell window</span></span>

<span data-ttu-id="db6c7-104">Если вы используете PowerShell для управления Microsoft 365, то можете одновременно открыть несколько сеансов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db6c7-104">When you use PowerShell to manage Microsoft 365, you can have multiple PowerShell sessions open at the same time.</span></span> <span data-ttu-id="db6c7-105">У вас могут быть разные окна PowerShell для управления учетными записями пользователей, SharePoint Online, Exchange Online, Skype для бизнеса Online, Microsoft Teams и Центром безопасности &amp; соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="db6c7-105">You might have different PowerShell windows to manage user accounts, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams, and the Security &amp; Compliance center.</span></span>
  
<span data-ttu-id="db6c7-106">Этот сценарий управления Microsoft 365 не назовешь удобным, поскольку в таком случае отсутствует возможность обмениваться данными между этими окнами для управления разными службами.</span><span class="sxs-lookup"><span data-stu-id="db6c7-106">This scenario isn't optimal for managing Microsoft 365, because you can't exchange data among those windows for cross-service management.</span></span> <span data-ttu-id="db6c7-107">В этой статье описывается, как использовать один экземпляр PowerShell для управления учетными записями Microsoft 365, Skype для бизнеса Online, Exchange Online, SharePoint Online, Microsoft Teams и Центром безопасности &amp; соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="db6c7-107">This article describes how to use a single instance of PowerShell to manage Microsoft 365 accounts, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span>

>[!Note]
><span data-ttu-id="db6c7-108">В этой статье приведены только команды для подключения к всемирному (+ GCC) облаку.</span><span class="sxs-lookup"><span data-stu-id="db6c7-108">This article currently only contains the commands to connect to the Worldwide (+GCC) cloud.</span></span> <span data-ttu-id="db6c7-109">Примечания содержат ссылки на статьи о подключении к другим облакам Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="db6c7-109">Notes provide links to articles about connecting to the other Microsoft 365 clouds.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="db6c7-110">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="db6c7-110">Before you begin</span></span>

<span data-ttu-id="db6c7-111">Существует ряд необходимых условий, которые нужно выполнить, прежде чем приступать к управлению всеми службами Microsoft 365 с помощью единого экземпляра PowerShell:</span><span class="sxs-lookup"><span data-stu-id="db6c7-111">Before you can manage all of Microsoft 365 from a single instance of PowerShell, consider the following prerequisites:</span></span>
  
- <span data-ttu-id="db6c7-112">Рабочая или учебная учетная запись Microsoft 365, которую вы используете, должна относится к роли администратора Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="db6c7-112">The Microsoft 365 work or school account that you use must be a member of a Microsoft 365 admin role.</span></span> <span data-ttu-id="db6c7-113">Дополнительные сведения см. в статье [О ролях администраторов](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="db6c7-113">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span> <span data-ttu-id="db6c7-114">Это требуется для PowerShell для Microsoft 365, но не обязательно для других служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="db6c7-114">This is a requirement for PowerShell for Microsoft 365, but not necessarily for all other Microsoft 365 services.</span></span>
    
- <span data-ttu-id="db6c7-115">Ниже приведены 64-разрядные версии Windows, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="db6c7-115">You can use the following 64-bit versions of Windows:</span></span>
    
  - <span data-ttu-id="db6c7-116">Windows 10;</span><span class="sxs-lookup"><span data-stu-id="db6c7-116">Windows 10</span></span>
    
  - <span data-ttu-id="db6c7-117">Windows 8.1 или Windows 8</span><span class="sxs-lookup"><span data-stu-id="db6c7-117">Windows 8.1 or Windows 8</span></span>
    
  - <span data-ttu-id="db6c7-118">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="db6c7-118">Windows Server 2019</span></span>
    
  - <span data-ttu-id="db6c7-119">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="db6c7-119">Windows Server 2016</span></span>
    
  - <span data-ttu-id="db6c7-120">Windows Server 2012 R2 или Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="db6c7-120">Windows Server 2012 R2 or Windows Server 2012</span></span>
    
  - <span data-ttu-id="db6c7-121">Windows 7 с пакетом обновления 1 (SP1)\*</span><span class="sxs-lookup"><span data-stu-id="db6c7-121">Windows 7 Service Pack 1 (SP1)\*</span></span>
    
  - <span data-ttu-id="db6c7-122">Windows Server 2008 R2 с пакетом обновления 1 (SP1)\*</span><span class="sxs-lookup"><span data-stu-id="db6c7-122">Windows Server 2008 R2 SP1\*</span></span>
    
    <span data-ttu-id="db6c7-123">\* Необходимо установить Microsoft .NET Framework 4.5.*x*, а затем — Windows Management Framework 3.0 или 4.0.</span><span class="sxs-lookup"><span data-stu-id="db6c7-123">\* You need to install Microsoft .NET Framework 4.5.*x* and then Windows Management Framework 3.0 or 4.0.</span></span> <span data-ttu-id="db6c7-124">Дополнительные сведения см. в статье [Windows Management Framework](https://docs.microsoft.com/powershell/scripting/windows-powershell/wmf/overview?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="db6c7-124">For more information, see [Windows Management Framework](https://docs.microsoft.com/powershell/scripting/windows-powershell/wmf/overview?view=powershell-7).</span></span>
    
    <span data-ttu-id="db6c7-125">Необходимо использовать именно 64-разрядную версию Windows, поскольку это обязательное требование для модуля Skype для бизнеса Online и одного из модулей Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="db6c7-125">You need to use a 64-bit version of Windows because of the requirements for the Skype for Business Online module and one of the Microsoft 365 modules.</span></span>
    
- <span data-ttu-id="db6c7-126">Необходимо установить модули, необходимые для Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype для бизнеса Online и Teams:</span><span class="sxs-lookup"><span data-stu-id="db6c7-126">You need to install the modules that are required for Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online and Teams:</span></span>
    
  - [<span data-ttu-id="db6c7-127">Azure Active Directory V2</span><span class="sxs-lookup"><span data-stu-id="db6c7-127">Azure Active Directory V2</span></span>](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  - [<span data-ttu-id="db6c7-128">Командная консоль SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="db6c7-128">SharePoint Online Management Shell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=255251)
  - [<span data-ttu-id="db6c7-129">Skype для бизнеса Online, модуль PowerShell</span><span class="sxs-lookup"><span data-stu-id="db6c7-129">Skype for Business Online, PowerShell Module</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
  - [<span data-ttu-id="db6c7-130">Exchange Online PowerShell V2</span><span class="sxs-lookup"><span data-stu-id="db6c7-130">Exchange Online PowerShell V2</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-v2-module)
  - [<span data-ttu-id="db6c7-131">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="db6c7-131">Teams PowerShell Overview</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  <span data-ttu-id="db6c7-132">Требуется настроить PowerShell для выполнения подписанных сценариев Skype для бизнеса Online и Центра безопасности &amp; соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="db6c7-132">PowerShell must be configured to run signed scripts for Skype for Business Online and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="db6c7-133">Выполните следующую команду в сеансе PowerShell с повышенными привилегиями (сеанс PowerShell, **запускаемый от имени администратора**).</span><span class="sxs-lookup"><span data-stu-id="db6c7-133">Run the following command in an elevated PowerShell session (a PowerShell session that you **Run as administrator**).</span></span>
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="exchange-online-and-security-amp-compliance-center-with-the-exchange-online-powershell-v2-module"></a><span data-ttu-id="db6c7-134">Использование Exchange Online и Центра безопасности &amp; соответствия требованиям вместе с модулем Exchange Online PowerShell V2</span><span class="sxs-lookup"><span data-stu-id="db6c7-134">Exchange Online and Security &amp; Compliance Center with the Exchange Online PowerShell V2 module</span></span>

<span data-ttu-id="db6c7-135">В процедурах этой статьи используется модуль Exchange Online PowerShell V2 для подключения к Exchange Online и Центру безопасности &amp; соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="db6c7-135">The procedures in this article use the Exchange Online PowerShell V2 module to connect to both Exchange Online and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="db6c7-136">Но в настоящее время вы не можете подключаться к обеим службам *в одном окне PowerShell*.</span><span class="sxs-lookup"><span data-stu-id="db6c7-136">But currently you can't connect to both *in the same PowerShell window*.</span></span> <span data-ttu-id="db6c7-137">Таким образом, вы должны выбрать подключение к одной из служб при настройке окна PowerShell для нескольких служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="db6c7-137">So you have to choose to connect to one or the other when you configure a PowerShell window for multiple Microsoft 365 services.</span></span>

## <a name="connection-steps-when-using-just-a-password"></a><span data-ttu-id="db6c7-138">Этапы подключения с использованием только пароля</span><span class="sxs-lookup"><span data-stu-id="db6c7-138">Connection steps when using just a password</span></span>

<span data-ttu-id="db6c7-139">Ниже описаны действия для подключения ко всем службам в одном окне PowerShell, если вы используете только пароль для входа в систему.</span><span class="sxs-lookup"><span data-stu-id="db6c7-139">Follow these steps to connect to all the services in a single PowerShell window when you're using just a password for sign-in.</span></span>
  
1. <span data-ttu-id="db6c7-140">Откройте Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db6c7-140">Open Windows PowerShell.</span></span>
    
2. <span data-ttu-id="db6c7-141">Выполните эту команду и введите свои учетные данные Microsoft 365 для рабочей или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="db6c7-141">Run this command and enter your Microsoft 365 work or school account credentials.</span></span>
    
   ```powershell
   $credential = Get-Credential
   ```

3. <span data-ttu-id="db6c7-142">Выполните эту команду для подключения к Azure AD с помощью модуля Azure Active Directory PowerShell для Graph.</span><span class="sxs-lookup"><span data-stu-id="db6c7-142">Run this command to connect to Azure AD by using the Azure Active Directory PowerShell for Graph module.</span></span>
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   <span data-ttu-id="db6c7-143">Или если вы используете модуль Microsoft Azure Active Directory для Windows PowerShell, выполните эту команду.</span><span class="sxs-lookup"><span data-stu-id="db6c7-143">Or if you're using the Microsoft Azure Active Directory Module for Windows PowerShell module, run this command.</span></span>
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > <span data-ttu-id="db6c7-144">В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты с компонентом *Msol* в имени.</span><span class="sxs-lookup"><span data-stu-id="db6c7-144">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="db6c7-145">Эти командлеты требуется запускать из PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db6c7-145">You must run these cmdlets from PowerShell.</span></span>

4. <span data-ttu-id="db6c7-146">Выполните приведенные ниже команды для подключения к SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="db6c7-146">Run these commands to connect to SharePoint Online.</span></span> <span data-ttu-id="db6c7-147">Введите название организации для вашего домена.</span><span class="sxs-lookup"><span data-stu-id="db6c7-147">Specify the organization name for your domain.</span></span> <span data-ttu-id="db6c7-148">Например, для "litwareinc\.onmicrosoft.com" значение названия организации — "litwareinc".</span><span class="sxs-lookup"><span data-stu-id="db6c7-148">For example, for "litwareinc\.onmicrosoft.com", the  organization name value is "litwareinc".</span></span>
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $Credential
   ```

5. <span data-ttu-id="db6c7-149">Выполните следующие команды для подключения к Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="db6c7-149">Run these commands to connect to Skype for Business Online.</span></span> <span data-ttu-id="db6c7-150">При первом подключении появится предупреждение об увеличении значения параметра `WSMan NetworkDelayms`.</span><span class="sxs-lookup"><span data-stu-id="db6c7-150">A warning about increasing the `WSMan NetworkDelayms` value will appear the first time that you connect.</span></span> <span data-ttu-id="db6c7-151">Игнорируйте его.</span><span class="sxs-lookup"><span data-stu-id="db6c7-151">Ignore it.</span></span>
     
   > [!Note]
   > <span data-ttu-id="db6c7-152">Соединитель Skype для бизнеса Online в настоящее время является частью последнего модуля Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db6c7-152">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="db6c7-153">Если вы используете последний общедоступный выпуск Teams PowerShell, вам не нужно устанавливать соединитель Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="db6c7-153">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
   
   ```powershell
   Import-Module MicrosoftTeams
   $sfboSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfboSession
   ```

6. <span data-ttu-id="db6c7-154">Выполните эту команду для подключения к Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="db6c7-154">Run this command to connect to Exchange Online.</span></span>
    
   ```powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -Credential $credential -ShowProgress $true
   ```

   > [!Note]
   > <span data-ttu-id="db6c7-155">Чтобы подключиться к Exchange Online для облаков Microsoft 365, отличных от всемирного облака, см. статью [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="db6c7-155">To connect to Exchange Online for Microsoft 365 clouds other than Worldwide, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

   <span data-ttu-id="db6c7-156">Или выполните следующие команды для подключения к Центру безопасности &amp; соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="db6c7-156">Alternatively, run these commands to connect to the Security &amp; Compliance Center.</span></span>
    
   ```powershell
   $acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
   Import-Module ExchangeOnlineManagement
   Connect-IPPSSession -UserPrincipalName $acctName
   ```

   > [!Note]
   > <span data-ttu-id="db6c7-157">Чтобы подключиться к Центру безопасности&amp; соответствия требованиям для облаков Microsoft 365, отличных от всемирного облака, см. статью [Подключение к Центру безопасности и соответствия требованиям PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="db6c7-157">To connect to the Security &amp; Compliance Center for Microsoft 365 clouds other than Worldwide, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

   <span data-ttu-id="db6c7-158">Выполните следующие команды для подключения к Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db6c7-158">Run these commands to connect to Teams PowerShell.</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > <span data-ttu-id="db6c7-159">Чтобы подключиться к облакам Microsoft Teams, отличным от *всемирного* облака, см. раздел [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams).</span><span class="sxs-lookup"><span data-stu-id="db6c7-159">To connect to Microsoft Teams clouds other than *Worldwide*, see [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams).</span></span>


### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="db6c7-160">Использование модуля Azure Active Directory PowerShell для Graph</span><span class="sxs-lookup"><span data-stu-id="db6c7-160">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="db6c7-161">Ниже в едином блоке перечислены команды для всех служб, *за исключением Центра безопасности &amp; соответствия требованиям*, при использовании модуля Azure Active Directory для Graph.</span><span class="sxs-lookup"><span data-stu-id="db6c7-161">Here are the commands for all the services *except Security &amp; Compliance Center* in a single block when you use the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="db6c7-162">Укажите доменное имя узла и запустите их одновременно.</span><span class="sxs-lookup"><span data-stu-id="db6c7-162">Specify the name of your domain host and run them all at the same time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="db6c7-163">Ниже в едином блоке перечислены команды для всех служб, *за исключением Exchange Online*, при использовании модуля Azure Active Directory PowerShell для Graph.</span><span class="sxs-lookup"><span data-stu-id="db6c7-163">Here are the commands for all the services *except Exchange Online* in a single block when you use the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="db6c7-164">Укажите доменное имя узла и UPN для входа, а затем запустите их одновременно.</span><span class="sxs-lookup"><span data-stu-id="db6c7-164">Specify the name of your domain host and the UPN for the sign-in and run them all at the same time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="db6c7-165">Модуль Microsoft Azure Active Directory для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="db6c7-165">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="db6c7-166">Ниже в едином блоке перечислены команды для всех служб, *за исключением Центра безопасности &amp; соответствия требованиям*, при использовании модуля Microsoft Azure Active Directory для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db6c7-166">Here are the commands for all the services *except Security &amp; Compliance Center* in a single block when you use the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="db6c7-167">Укажите доменное имя узла и запустите их одновременно.</span><span class="sxs-lookup"><span data-stu-id="db6c7-167">Specify the name of your domain host and run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-MsolService -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="db6c7-168">Ниже в едином блоке перечислены команды для всех служб, *за исключением Exchange Online*, при использовании модуля Microsoft Azure Active Directory для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db6c7-168">Here are the commands for all the services *except Exchange Online* in a single block when you use the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="db6c7-169">Укажите доменное имя узла и UPN для входа, а затем запустите их одновременно.</span><span class="sxs-lookup"><span data-stu-id="db6c7-169">Specify the name of your domain host and the UPN for the sign-in and run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```
## <a name="connection-steps-when-using-multi-factor-authentication"></a><span data-ttu-id="db6c7-170">Этапы подключения при использовании многофакторной идентификации</span><span class="sxs-lookup"><span data-stu-id="db6c7-170">Connection steps when using multi-factor authentication</span></span>

### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="db6c7-171">Использование модуля Azure Active Directory PowerShell для Graph</span><span class="sxs-lookup"><span data-stu-id="db6c7-171">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="db6c7-172">Ниже в едином блоке перечислены все команды, которые можно использовать для подключения к нескольким службам Microsoft 365, *за исключением Центра безопасности &amp; соответствия требованиям*, при использовании многофакторной проверки подлинности с помощью модуля Azure Active Directory PowerShell для Graph.</span><span class="sxs-lookup"><span data-stu-id="db6c7-172">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Security &amp; Compliance Center* when you use multi-factor authentication with the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession
Import-PSSession $sfboSession
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
<span data-ttu-id="db6c7-173">Ниже в едином блоке перечислены все команды, которые можно использовать для подключения к нескольким службам Microsoft 365, *за исключением Exchange Online*, с помощью многофакторной проверки подлинности при использовании модуля Azure Active Directory PowerShell для Graph.</span><span class="sxs-lookup"><span data-stu-id="db6c7-173">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Exchange Online* with multi-factor authentication when you use the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession
Import-PSSession $sfboSession
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="db6c7-174">Модуль Microsoft Azure Active Directory для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="db6c7-174">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="db6c7-175">Ниже в едином блоке перечислены все команды, которые можно использовать для подключения к нескольким службам Microsoft 365, *за исключением Центра безопасности &amp; соответствия требованиям*, при использовании многофакторной проверки подлинности с помощью модуля Microsoft Azure Active Directory для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db6c7-175">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Security &amp; Compliance Center* when you use multi-factor authentication with the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession
Import-PSSession $sfboSession
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
<span data-ttu-id="db6c7-176">Ниже в едином блоке перечислены все команды, которые можно использовать для подключения к нескольким службам Microsoft 365, *за исключением Exchange Online*, при использовании многофакторной проверки подлинности с помощью модуля Microsoft Azure Active Directory для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db6c7-176">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Exchange Online* when you use multi-factor authentication with the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession
Import-PSSession $sfboSession
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

## <a name="close-the-powershell-window"></a><span data-ttu-id="db6c7-177">Закрытие окна PowerShell</span><span class="sxs-lookup"><span data-stu-id="db6c7-177">Close the PowerShell window</span></span>

<span data-ttu-id="db6c7-178">Чтобы закрыть окно PowerShell, выполните эту команду для завершения всех активных сеансов в Skype для бизнеса Online, SharePoint Online и Teams:</span><span class="sxs-lookup"><span data-stu-id="db6c7-178">To close down the PowerShell window, run this command to remove the active sessions to Skype for Business Online, SharePoint Online, and Teams:</span></span>
  
```powershell
Remove-PSSession $sfboSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```

## <a name="see-also"></a><span data-ttu-id="db6c7-179">См. также</span><span class="sxs-lookup"><span data-stu-id="db6c7-179">See also</span></span>

- [<span data-ttu-id="db6c7-180">Подключение к Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="db6c7-180">Connect to Microsoft 365 with PowerShell</span></span>](connect-to-microsoft-365-powershell.md)
- [<span data-ttu-id="db6c7-181">Управление SharePoint Online с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="db6c7-181">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [<span data-ttu-id="db6c7-182">Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="db6c7-182">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
