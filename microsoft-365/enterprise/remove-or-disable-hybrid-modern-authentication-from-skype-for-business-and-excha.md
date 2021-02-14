---
title: Удаление гибридной современной проверки подлинности из Skype для бизнеса и Exchange или ее отключение
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/3/2017
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5a91b9e3-1508-475b-93e0-710fa5d5cd2d
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: В этой статье объясняется, как удалить или отключить гибридную современную проверку подлинности в Skype для бизнеса и Exchange.
ms.openlocfilehash: 70f62b9b2165464837aa1dea0e12854df116efe0
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547100"
---
# <a name="removing-or-disabling-hybrid-modern-authentication-from-skype-for-business-and-exchange"></a>Удаление гибридной современной проверки подлинности из Skype для бизнеса и Exchange или ее отключение

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Если вы включили гибридную современную проверку подлинности (HMA) только для того, чтобы найти ее неподходящей для текущей среды, вы можете отключить HMA. В этой статье объясняется, как это сделать.
  
## <a name="who-is-this-article-for"></a>Для кого эта статья?

If you've enabled Modern Authentication in Skype for Business Online or On-premises, and/or Exchange Online or On-premises and found you need to disable HMA, these steps are for you.

> [!IMPORTANT]
> См. статью "Топологии[Skype](https://technet.microsoft.com/library/mt803262.aspx)для бизнеса, поддерживаемые современной проверкой подлинности", если вы в Skype для бизнеса Online или локальной сети, у вас есть HMA со смешанной топологией, и перед началом работы необходимо посмотреть на поддерживаемые топологии.
  
## <a name="how-to-disable-hybrid-modern-authentication-exchange"></a>Отключение гибридной современной проверки подлинности (Exchange)

1. **Exchange On-premises**: Open the Exchange Management Shell and run the following commands: 

```powershell
Set-OrganizationConfig -OAuth2ClientProfileEnabled $false
Set-AuthServer -Identity evoSTS -IsDefaultAuthorizationEndpoint $false
```

2. **Exchange Online**: [подключение к Exchange Online с](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) помощью удаленной powerShell. Чтобы включить флаг  *OAuth2ClientProfileEnabled*  в "false", запустите следующую команду:

```powershell    
Set-OrganizationConfig -OAuth2ClientProfileEnabled:$false
```
    
## <a name="how-to-disable-hybrid-modern-authentication-skype-for-business"></a>Отключение гибридной современной проверки подлинности (Skype для бизнеса)

1. **Локальное решение Skype** для бизнеса: в командной оболочке Skype для бизнеса запустите следующие команды:

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity ""
```

2. **Skype для бизнеса Online:** [подключение к Skype для бизнеса Online с](manage-skype-for-business-online-with-microsoft-365-powershell.md) помощью удаленной powerShell. Чтобы отключить современную проверку подлинности, запустите следующую команду:

```powershell    
Set-CsOAuthConfiguration -ClientAdalAuthOverride Disallowed
```

[Ссылка на обзор современной проверки подлинности.](hybrid-modern-auth-overview.md) 
  

