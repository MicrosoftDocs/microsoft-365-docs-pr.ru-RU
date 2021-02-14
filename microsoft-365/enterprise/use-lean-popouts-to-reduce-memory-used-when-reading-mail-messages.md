---
title: Используйте нежирные всплывающие окни, чтобы уменьшить объем памяти, используемый при чтении сообщений электронной почты
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
description: В этой статье содержатся сведения об использовании нежирных всплывающих сообщений для повышения производительности скачивания сообщений в Outlook в Интернете.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7bf53464ac6b2783fbbfc335fd4ff73dbe4435fb
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693446"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a><span data-ttu-id="236f6-103">Используйте нежирные всплывающие окни, чтобы уменьшить объем памяти, используемый при чтении сообщений электронной почты</span><span class="sxs-lookup"><span data-stu-id="236f6-103">Use lean popouts to reduce memory used when reading mail messages</span></span>

<span data-ttu-id="236f6-104">В этой статье содержатся сведения о повышении производительности скачивания сообщений в Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="236f6-104">This article contains information for improving message download performance in Outlook on the web.</span></span> <span data-ttu-id="236f6-105">Эта статья входит в состав проекта "Планирование сети и [настройка производительности для Office 365".](https://aka.ms/tune)</span><span class="sxs-lookup"><span data-stu-id="236f6-105">This article is part of the [Network planning and performance tuning for Office 365](https://aka.ms/tune) project.</span></span>
  
<span data-ttu-id="236f6-106">Как глобальный администратор Office 365 вы можете настроить Outlook в Интернете для доставки небольших, менее объемных в памяти версий определенных сообщений электронной почты в Microsoft Edge или Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="236f6-106">As an Office 365 global administrator, you can configure Outlook on the web to deliver _lean popouts_, a smaller, less memory-intensive version of certain email messages in Microsoft Edge or Internet Explorer.</span></span> <span data-ttu-id="236f6-107">При настройке нестрогого всплывающих элементов для Outlook в Интернете загружаются серверные компоненты, оптимизируемые производительностью.</span><span class="sxs-lookup"><span data-stu-id="236f6-107">When lean popouts are configured for Outlook on the web, server-side rendered components are loaded that optimize performance.</span></span>
  
> [!NOTE]
> <span data-ttu-id="236f6-108">С марта 2018 г. для сообщений с ограничениями прав на использование, таких как управление правами на доступ к данным (IRM), недоступны ненамеренные всплывающие сообщения.</span><span class="sxs-lookup"><span data-stu-id="236f6-108">As of March 2018, lean popouts are not available for messages that specify usage rights restrictions, such as Information Rights Management (IRM).</span></span>
  
<span data-ttu-id="236f6-109">Эти функции продолжат работать в главном окне, но недоступны в нежирных всплывающих окнах:</span><span class="sxs-lookup"><span data-stu-id="236f6-109">These features will continue to work in the main window but are not available in lean popouts:</span></span>
  
- <span data-ttu-id="236f6-110">Надстройки Outlook</span><span class="sxs-lookup"><span data-stu-id="236f6-110">Outlook add-ins</span></span>
  
- <span data-ttu-id="236f6-111">Присутствие в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="236f6-111">Skype for Business presence</span></span>
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a><span data-ttu-id="236f6-112">Настройка нестрогого всплывающих всплывающих папок для всех пользователей в организации Office 365</span><span class="sxs-lookup"><span data-stu-id="236f6-112">To configure lean popouts for all users within your Office 365 organization</span></span>
  
1. <span data-ttu-id="236f6-113">[Подключение к Exchange Online с помощью удаленной powerShell.](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx )</span><span class="sxs-lookup"><span data-stu-id="236f6-113">[Connect to Exchange Online Using Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx ).</span></span>
  
2. <span data-ttu-id="236f6-114">Запустите [cmdlet Set-OrganizationConfig](https://technet.microsoft.com/library/aa997443%28v=exchg.160%29.aspx) с параметром LeanPopoutEnabled следующим образом:</span><span class="sxs-lookup"><span data-stu-id="236f6-114">Run the [Set-OrganizationConfig](https://technet.microsoft.com/library/aa997443%28v=exchg.160%29.aspx) cmdlet with the LeanPopoutEnabled parameter as follows:</span></span>

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  <span data-ttu-id="236f6-115">Например, чтобы включить нежирные всплывающие окни для всех пользователей в организации:</span><span class="sxs-lookup"><span data-stu-id="236f6-115">For example, to enable lean popouts for all users in your organization:</span></span>
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  <span data-ttu-id="236f6-116">Чтобы отключить нежирные всплывающие окни для всех пользователей в организации:</span><span class="sxs-lookup"><span data-stu-id="236f6-116">To disable lean popouts for all users in your organization:</span></span>

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```
