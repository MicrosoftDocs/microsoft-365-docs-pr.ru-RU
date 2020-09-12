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
description: В этой статье объясняется, как удалить или отключить гибридную современные проверки подлинности из Skype для бизнеса и Exchange.
ms.openlocfilehash: 70f62b9b2165464837aa1dea0e12854df116efe0
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547100"
---
# <a name="removing-or-disabling-hybrid-modern-authentication-from-skype-for-business-and-exchange"></a>Удаление гибридной современной проверки подлинности из Skype для бизнеса и Exchange или ее отключение

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Если Гибридная современная проверка подлинности (HMA) включена только для того, чтобы найти непригодную для текущей среды, можно отключить HMA. В этой статье описывается, как это сделать.
  
## <a name="who-is-this-article-for"></a>Для кого предназначена эта статья?

Если вы включили современные проверки подлинности в Skype для бизнеса Online или локальной среде, а также на сервере Exchange Online или в локальной среде, и вам нужно отключить сегмент HMA, выполните указанные ниже действия.

> [!IMPORTANT]
> Ознакомьтесь со статьей "[топологии Skype для бизнеса, поддерживаемые с современной проверкой подлинности](https://technet.microsoft.com/library/mt803262.aspx)", если вы находитесь в Skype для бизнеса Online или в локальной среде, у вас есть смешанная топология HMA, и вам нужно взглянуть на поддерживаемые топологии перед началом работы.
  
## <a name="how-to-disable-hybrid-modern-authentication-exchange"></a>Как отключить гибридную современные проверки подлинности (Exchange)

1. **Локальная служба Exchange**: Откройте командную консоль Exchange и выполните следующие команды: 

```powershell
Set-OrganizationConfig -OAuth2ClientProfileEnabled $false
Set-AuthServer -Identity evoSTS -IsDefaultAuthorizationEndpoint $false
```

2. **Exchange Online**: [Подключение к Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) с помощью удаленного сеанса PowerShell. Выполните следующую команду, чтобы превратить флаг  *OAuth2ClientProfileEnabled*  в значение false:

```powershell    
Set-OrganizationConfig -OAuth2ClientProfileEnabled:$false
```
    
## <a name="how-to-disable-hybrid-modern-authentication-skype-for-business"></a>Как отключить гибридную современные проверки подлинности (Skype для бизнеса)

1. **Локальная среда Skype для бизнеса**: выполните следующие команды в командной консоли Skype для бизнеса:

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity ""
```

2. **Skype для бизнеса Online**: [Подключение к Skype для бизнеса Online](manage-skype-for-business-online-with-microsoft-365-powershell.md) с помощью удаленного сеанса PowerShell. Выполните следующую команду, чтобы отключить современные проверки подлинности:

```powershell    
Set-CsOAuthConfiguration -ClientAdalAuthOverride Disallowed
```

[Выполните обратное соединение с обзором современной проверки подлинности](hybrid-modern-auth-overview.md) . 
  

