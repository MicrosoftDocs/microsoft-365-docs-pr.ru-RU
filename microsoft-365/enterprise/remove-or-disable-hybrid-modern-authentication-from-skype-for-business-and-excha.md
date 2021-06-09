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
description: В этой статье рассказывается, как удалить или отключить гибридную современную проверку подлинности из Skype для бизнеса и Exchange.
ms.openlocfilehash: 9442ef3e19d0835bfd59f27ec425e36fd7dfcf7a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927292"
---
# <a name="removing-or-disabling-hybrid-modern-authentication-from-skype-for-business-and-exchange"></a>Удаление гибридной современной проверки подлинности из Skype для бизнеса и Exchange или ее отключение

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Если вы включили гибридную современную проверку подлинности (HMA) только для того, чтобы найти ее непригодной для текущей среды, вы можете отключить HMA. В этой статье объясняется, как.
  
## <a name="who-is-this-article-for"></a>Кто для этой статьи?

Если вы включили современную проверку подлинности в Skype для бизнеса Online или локальной, и/или Exchange Online или локальной и обнаружили, что необходимо отключить HMA, эти действия будут для вас.

> [!IMPORTANT]
> См.[](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)Skype для бизнеса топологии, поддерживаемые статьей Современная проверка подлинности, если вы в Skype для бизнеса Online или локально, имеете смешанную топологию HMA, и перед началом работы необходимо взглянуть на поддерживаемые топологии.
  
## <a name="how-to-disable-hybrid-modern-authentication-exchange"></a>Отключение гибридной современной проверки подлинности (Exchange)

1. **Exchange** локальной области: Откройте Exchange командную команду и запустите следующие команды: 

```powershell
Set-OrganizationConfig -OAuth2ClientProfileEnabled $false
Set-AuthServer -Identity evoSTS -IsDefaultAuthorizationEndpoint $false
```

2. **Exchange Online**: [Подключение Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell) с удаленной powerShell. Запустите следующую команду, чтобы превратить флаг  *OAuth2ClientProfileEnabled*  в "false":

```powershell    
Set-OrganizationConfig -OAuth2ClientProfileEnabled:$false
```
    
## <a name="how-to-disable-hybrid-modern-authentication-skype-for-business"></a>Отключение гибридной современной проверки подлинности (Skype для бизнеса)

1. **Skype для бизнеса** локальной области: запустите следующие команды в Skype для бизнеса Командная оболочка:

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity ""
```

2. **Skype для бизнеса Online**: [Подключение Skype для бизнеса Online с](manage-skype-for-business-online-with-microsoft-365-powershell.md) удаленной powerShell. Запустите следующую команду, чтобы отключить современную проверку подлинности:

```powershell    
Set-CsOAuthConfiguration -ClientAdalAuthOverride Disallowed
```

[Ссылка на обзор современной проверки подлинности.](hybrid-modern-auth-overview.md) 
