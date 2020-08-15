---
title: Использование экономичных всплывающих окон для уменьшения объема памяти, используемой при чтении почтовых сообщений
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a6d6ba01-2562-4c3d-a8f1-78748dd506cf
f1.keywords:
- NOCSH
description: В этой статье содержатся сведения об использовании экономичных всплывающих окон для улучшения скорости загрузки сообщений в Outlook в Интернете.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7bf53464ac6b2783fbbfc335fd4ff73dbe4435fb
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693446"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a><span data-ttu-id="c0dba-103">Использование экономичных всплывающих окон для уменьшения объема памяти, используемой при чтении почтовых сообщений</span><span class="sxs-lookup"><span data-stu-id="c0dba-103">Use lean popouts to reduce memory used when reading mail messages</span></span>

<span data-ttu-id="c0dba-104">В этой статье содержатся сведения о том, как улучшить производительность загрузки сообщений в Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="c0dba-104">This article contains information for improving message download performance in Outlook on the web.</span></span> <span data-ttu-id="c0dba-105">Эта статья является частью [планирования сети и настройки производительности для проекта Office 365](https://aka.ms/tune) .</span><span class="sxs-lookup"><span data-stu-id="c0dba-105">This article is part of the [Network planning and performance tuning for Office 365](https://aka.ms/tune) project.</span></span>
  
<span data-ttu-id="c0dba-106">Как глобальный администратор Office 365 вы можете настроить Outlook в Интернете, чтобы обеспечить _экономичное всплывающих окон_, меньшее количество сообщений электронной почты в Microsoft EDGE или Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="c0dba-106">As an Office 365 global administrator, you can configure Outlook on the web to deliver _lean popouts_, a smaller, less memory-intensive version of certain email messages in Microsoft Edge or Internet Explorer.</span></span> <span data-ttu-id="c0dba-107">Когда экономичный всплывающих окон настраивается для Outlook в Интернете, загружаются серверные компоненты, которые оптимизируют производительность.</span><span class="sxs-lookup"><span data-stu-id="c0dba-107">When lean popouts are configured for Outlook on the web, server-side rendered components are loaded that optimize performance.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c0dba-108">За март 2018, экономичный всплывающих окон недоступен для сообщений, в которых указаны ограничения прав на использование, например, управления правами на доступ к данным (IRM).</span><span class="sxs-lookup"><span data-stu-id="c0dba-108">As of March 2018, lean popouts are not available for messages that specify usage rights restrictions, such as Information Rights Management (IRM).</span></span>
  
<span data-ttu-id="c0dba-109">Эти функции продолжат работу в главном окне, но недоступны в экономичных всплывающих окон:</span><span class="sxs-lookup"><span data-stu-id="c0dba-109">These features will continue to work in the main window but are not available in lean popouts:</span></span>
  
- <span data-ttu-id="c0dba-110">Надстройки Outlook</span><span class="sxs-lookup"><span data-stu-id="c0dba-110">Outlook add-ins</span></span>
  
- <span data-ttu-id="c0dba-111">Присутствие в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c0dba-111">Skype for Business presence</span></span>
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a><span data-ttu-id="c0dba-112">Настройка экономичного всплывающих окон для всех пользователей в организации Office 365</span><span class="sxs-lookup"><span data-stu-id="c0dba-112">To configure lean popouts for all users within your Office 365 organization</span></span>
  
1. <span data-ttu-id="c0dba-113">[Подключитесь к Exchange Online с помощью удаленной оболочки PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx ).</span><span class="sxs-lookup"><span data-stu-id="c0dba-113">[Connect to Exchange Online Using Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx ).</span></span>
  
2. <span data-ttu-id="c0dba-114">Выполните командлет [Set – OrganizationConfig](https://technet.microsoft.com/library/aa997443%28v=exchg.160%29.aspx) с параметром леанпопаутенаблед следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c0dba-114">Run the [Set-OrganizationConfig](https://technet.microsoft.com/library/aa997443%28v=exchg.160%29.aspx) cmdlet with the LeanPopoutEnabled parameter as follows:</span></span>

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  <span data-ttu-id="c0dba-115">Например, чтобы включить экономичный всплывающих окон для всех пользователей в Организации:</span><span class="sxs-lookup"><span data-stu-id="c0dba-115">For example, to enable lean popouts for all users in your organization:</span></span>
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  <span data-ttu-id="c0dba-116">Чтобы отключить экономичный всплывающих окон для всех пользователей в Организации:</span><span class="sxs-lookup"><span data-stu-id="c0dba-116">To disable lean popouts for all users in your organization:</span></span>

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```
