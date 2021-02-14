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
# <a name="removing-or-disabling-hybrid-modern-authentication-from-skype-for-business-and-exchange"></a><span data-ttu-id="4abc6-103">Удаление гибридной современной проверки подлинности из Skype для бизнеса и Exchange или ее отключение</span><span class="sxs-lookup"><span data-stu-id="4abc6-103">Removing or disabling Hybrid Modern Authentication from Skype for Business and Exchange</span></span>

<span data-ttu-id="4abc6-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="4abc6-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="4abc6-105">Если вы включили гибридную современную проверку подлинности (HMA) только для того, чтобы найти ее неподходящей для текущей среды, вы можете отключить HMA.</span><span class="sxs-lookup"><span data-stu-id="4abc6-105">If you've enabled Hybrid Modern Authentication (HMA) only to find it's unsuitable for your current environment, you can disable HMA.</span></span> <span data-ttu-id="4abc6-106">В этой статье объясняется, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="4abc6-106">This article explains how.</span></span>
  
## <a name="who-is-this-article-for"></a><span data-ttu-id="4abc6-107">Для кого эта статья?</span><span class="sxs-lookup"><span data-stu-id="4abc6-107">Who is this article for?</span></span>

<span data-ttu-id="4abc6-108">If you've enabled Modern Authentication in Skype for Business Online or On-premises, and/or Exchange Online or On-premises and found you need to disable HMA, these steps are for you.</span><span class="sxs-lookup"><span data-stu-id="4abc6-108">If you've enabled Modern Authentication in Skype for Business Online or On-premises, and/or Exchange Online or On-premises and found you need to disable HMA, these steps are for you.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4abc6-109">См. статью "Топологии[Skype](https://technet.microsoft.com/library/mt803262.aspx)для бизнеса, поддерживаемые современной проверкой подлинности", если вы в Skype для бизнеса Online или локальной сети, у вас есть HMA со смешанной топологией, и перед началом работы необходимо посмотреть на поддерживаемые топологии.</span><span class="sxs-lookup"><span data-stu-id="4abc6-109">See the '[Skype for Business topologies supported with Modern Authentication](https://technet.microsoft.com/library/mt803262.aspx)' article if you're in Skype for Business Online or On-premises, have a mixed-topology HMA, and need to look at supported topologies before you begin.</span></span>
  
## <a name="how-to-disable-hybrid-modern-authentication-exchange"></a><span data-ttu-id="4abc6-110">Отключение гибридной современной проверки подлинности (Exchange)</span><span class="sxs-lookup"><span data-stu-id="4abc6-110">How to disable Hybrid Modern Authentication (Exchange)</span></span>

1. <span data-ttu-id="4abc6-111">**Exchange On-premises**: Open the Exchange Management Shell and run the following commands:</span><span class="sxs-lookup"><span data-stu-id="4abc6-111">**Exchange On-premises**: Open the Exchange Management Shell and run the following commands:</span></span> 

```powershell
Set-OrganizationConfig -OAuth2ClientProfileEnabled $false
Set-AuthServer -Identity evoSTS -IsDefaultAuthorizationEndpoint $false
```

2. <span data-ttu-id="4abc6-112">**Exchange Online**: [подключение к Exchange Online с](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) помощью удаленной powerShell.</span><span class="sxs-lookup"><span data-stu-id="4abc6-112">**Exchange Online**: [Connect to Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) with Remote PowerShell.</span></span> <span data-ttu-id="4abc6-113">Чтобы включить флаг  *OAuth2ClientProfileEnabled*  в "false", запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4abc6-113">Run the following command to turn your  *OAuth2ClientProfileEnabled*  flag to 'false':</span></span>

```powershell    
Set-OrganizationConfig -OAuth2ClientProfileEnabled:$false
```
    
## <a name="how-to-disable-hybrid-modern-authentication-skype-for-business"></a><span data-ttu-id="4abc6-114">Отключение гибридной современной проверки подлинности (Skype для бизнеса)</span><span class="sxs-lookup"><span data-stu-id="4abc6-114">How to disable Hybrid Modern Authentication (Skype for Business)</span></span>

1. <span data-ttu-id="4abc6-115">**Локальное решение Skype** для бизнеса: в командной оболочке Skype для бизнеса запустите следующие команды:</span><span class="sxs-lookup"><span data-stu-id="4abc6-115">**Skype for Business On-premises**: Run the following commands in Skype for Business Management Shell:</span></span>

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity ""
```

2. <span data-ttu-id="4abc6-116">**Skype для бизнеса Online:** [подключение к Skype для бизнеса Online с](manage-skype-for-business-online-with-microsoft-365-powershell.md) помощью удаленной powerShell.</span><span class="sxs-lookup"><span data-stu-id="4abc6-116">**Skype for Business Online**: [Connect to Skype for Business Online](manage-skype-for-business-online-with-microsoft-365-powershell.md) with Remote PowerShell.</span></span> <span data-ttu-id="4abc6-117">Чтобы отключить современную проверку подлинности, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4abc6-117">Run the following command to disable Modern Authentication:</span></span>

```powershell    
Set-CsOAuthConfiguration -ClientAdalAuthOverride Disallowed
```

<span data-ttu-id="4abc6-118">[Ссылка на обзор современной проверки подлинности.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="4abc6-118">[Link back to the Modern Authentication overview](hybrid-modern-auth-overview.md) .</span></span> 
  

