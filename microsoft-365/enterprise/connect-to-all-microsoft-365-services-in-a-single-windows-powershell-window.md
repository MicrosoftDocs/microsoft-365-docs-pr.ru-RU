---
title: Подключение ко всем службам Microsoft 365 с помощью единого окна PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/26/2020
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
ms.openlocfilehash: af676434017cbe7025baa5e8509e6203a5d59674
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307629"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a>Подключение ко всем службам Microsoft 365 с помощью единого окна PowerShell

При использовании PowerShell для управления Microsoft 365 можно одновременно открывать различные сеансы PowerShell в разных окнах PowerShell, соответствующих задачам управления учетными записями пользователей, SharePoint Online, Exchange Online, Skype для бизнеса Online, Microsoft Teams и Центру безопасности &amp; соответствия требованиям. 
  
Этот способ управления Microsoft 365 не назовешь удобным, поскольку в таком случае отсутствует возможность обмениваться данными между этими окнами для управления разными службами. В этой статье описывается, как использовать один экземпляр PowerShell, с помощью которого можно управлять учетными записями Microsoft 365, Skype для бизнеса Online, Exchange Online, SharePoint Online, Microsoft Teams и Центром безопасности &amp; соответствия требованиям.

>[!Note]
>В этой статье приведены только команды для подключения к всемирному (+ GCC) облаку. Примечания содержат ссылки на статьи с информацией о подключении к другим облакам Microsoft 365.
>

## <a name="before-you-begin"></a>Прежде чем начать

Существует ряд необходимых условий, которые нужно выполнить, прежде чем приступать к управлению всеми службами Microsoft 365 с помощью единого экземпляра PowerShell:
  
- Рабочая или учебная учетная запись Microsoft 365, которую вы используете для выполнения этих действий, должна входить в роль администратора Microsoft 365. Дополнительные сведения см. в статье [О ролях администраторов](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide). Это требование для PowerShell для Microsoft 365, но не обязательно для других служб Microsoft 365.
    
- Ниже приведены 64-разрядные версии Windows, которые можно использовать.
    
  - Windows 10;
    
  - Windows 8.1 или Windows 8
    
  - Windows Server 2019
    
  - Windows Server 2016
    
  - Windows Server 2012 R2 или Windows Server 2012
    
  - Windows 7 с пакетом обновления 1 (SP1)*
    
  - Windows Server 2008 R2 с пакетом обновления 1 (SP1)*
    
    \* Необходимо установить Microsoft .NET Framework 4.5.*x*, а затем — Windows Management Framework 3.0 или Windows Management Framework 4.0. Подробнее см. [Установка .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868), [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) или[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344).
    
    Необходимо использовать именно 64-разрядную версию Windows, поскольку это обязательное требование для модуля Skype для бизнеса Online и одного из модулей Microsoft 365.
    
- Необходимо установить модули, необходимые для Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype для бизнеса Online и Teams:
    
   - [Azure Active Directory V2](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
   - [Командная консоль SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkId=255251)
   - [Skype для бизнеса Online, модуль PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=532439)
   - [Exchange Online PowerShell V2](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module)
   - [Обзор PowerShell в Teams](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  Необходимо настроить PowerShell для выполнения подписанных сценариев Skype для бизнеса Online и Центра безопасности &amp; соответствия требованиям. Для этого выполните следующую команду в сеансе PowerShell с повышенными привилегиями (открыв окно PowerShell с помощью команды **Запуск от имени администратора**).
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="connection-steps-when-using-just-a-password"></a>Этапы подключения только с использованием пароля

Ниже описаны действия, которые необходимо выполнить для подключения ко всем службам в одном окне PowerShell, если вы используете только пароль для входа в систему.
  
1. Откройте Windows PowerShell.
    
2. Выполните эту команду и введите свои учетные данные Microsoft 365 для рабочей или учебной учетной записи.
    
   ```powershell
   $credential = Get-Credential
   ```

3. Выполните эту команду для подключения к Azure AD с помощью модуля Azure Active Directory PowerShell для Graph.
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   Или же, если вы используете модуль Microsoft Azure Active Directory для PowerShell, выполните эту команду.
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для PowerShell и командлеты с компонентом **Msol** в имени. Чтобы использовать эти командлеты, необходимо запустить их из PowerShell.

4. Выполните приведенные ниже команды для подключения к SharePoint Online. Введите название организации для вашего домена. Например, для "litwareinc.onmicrosoft.com", значение названия организации — "litwareinc".
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $userCredential
   ```

5. Выполните следующие команды ля подключения к Skype для бизнеса Online. При первом подключении появится предупреждение об увеличении значения параметра `WSMan NetworkDelayms`. Можно смело пропустить это предупреждение.
     
   ```powershell
   Import-Module SkypeOnlineConnector
   $sfboSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfboSession
   ```

6. Выполните эту команду для подключения к Exchange Online.
    
   ```powershell
   Connect-ExchangeOnline -Credential $credential -ShowProgress $true
   ```

   > [!Note]
   > Чтобы подключиться к Exchange Online для не всемирных облаков Microsoft 365, используйте параметр **-ExchangeEnvironmentName**. Дополнительные сведения см. в разделе[Connect-ExchangeOnline](https://docs.microsoft.com/powershell/module/exchange/powershell-v2-module/connect-exchangeonline?view=exchange-ps)

7. Выполните следующие команды для подключения к Teams PowerShell.
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > Чтобы подключиться к облакам Microsoft Teams, отличным от всемирного облака, см. раздел [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps).

8. Выполните следующие команды для подключения к Центру безопасности &amp; соответствия требованиям.
    
   ```powershell
   $SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $credential -Authentication "Basic" -AllowRedirection
   Import-PSSession $SccSession -Prefix cc
   ```

   > [!Note]
   > Чтобы подключиться к Центру безопасности&amp; соответствия требованиям для облаков Microsoft 365, отличных от всемирного облака, см. статью раздел [Подключение к Центру безопасности и соответствия требованиям PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

Ниже в едином блоке перечислены все команды при использовании модуля Azure Active Directory PowerShell для Graph. Укажите доменное имя узла, а затем запустите их одновременно.
  
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

Или можно использовать перечисленные в едином блоке команды при применении модуля Microsoft Azure Active Directory для PowerShell. Укажите доменное имя узла, а затем запустите их одновременно.
  
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

Когда вы будете готовы закрыть окно PowerShell, выполните эту команду, чтобы удалить активные сеансы в Skype для бизнеса Online, SharePoint Online, Центре безопасности &amp; соответствия требованиям, а также в Teams:
  
```powershell
Remove-PSSession $sfboSession ; Remove-PSSession $SccSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```

## <a name="connection-steps-when-using-multi-factor-authentication"></a>Этапы подключения при использовании многофакторной проверки подлинности

Ниже в едином блоке перечислены все команды для подключения к Azure AD, SharePoint Online, Skype для бизнеса, Exchange Online и Teams с использованием многофакторной проверки подлинности в одном окне с помощью модуля Azure Active Directory PowerShell для Graph. Укажите имя участника-пользователя (UPN) для учетной записи пользователя и доменное имя узла, а затем запустите их одновременно.

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

Или можно использовать перечисленные команды при применении модуля Microsoft Azure Active Directory для PowerShell.

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

Сведения о подключении к Центру безопасности &amp; соответствия требованиям с использованием многофакторной проверки подлинности см. в разделе[Подключение к Центру безопасности и соответствия требованиям с использованием многофакторной проверки подлинности](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell?view=exchange-ps):

## <a name="see-also"></a>См. также

- [Подключение к Microsoft 365 с помощью PowerShell](connect-to-microsoft-365-powershell.md)
- [Управление SharePoint Online с помощью PowerShell](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
