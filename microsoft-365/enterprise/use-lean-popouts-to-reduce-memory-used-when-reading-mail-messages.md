---
title: Используйте постные всплывающие окантовки для уменьшения памяти, используемой при чтении сообщений почты
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
description: В этой статье содержатся сведения об использовании постных всплывающих сообщений для повышения производительности скачивания сообщений Outlook в Интернете.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0fec3e0267b7299e34de541a184cf92e99e260f1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925260"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a><span data-ttu-id="d7000-103">Используйте постные всплывающие окантовки для уменьшения памяти, используемой при чтении сообщений почты</span><span class="sxs-lookup"><span data-stu-id="d7000-103">Use lean popouts to reduce memory used when reading mail messages</span></span>

<span data-ttu-id="d7000-104">В этой статье содержатся сведения о повышении производительности скачивания сообщений Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="d7000-104">This article contains information for improving message download performance in Outlook on the web.</span></span> <span data-ttu-id="d7000-105">Эта статья является частью [сетевого планирования и](./network-planning-and-performance.md) настройки производительности для Office 365 проекта.</span><span class="sxs-lookup"><span data-stu-id="d7000-105">This article is part of the [Network planning and performance tuning for Office 365](./network-planning-and-performance.md) project.</span></span>
  
<span data-ttu-id="d7000-106">В качестве Office 365 глобального администратора можно настроить Outlook в Интернете для доставки постных всплывающих сообщений _,_ меньшей и менее интенсивной памяти некоторых сообщений электронной почты в Microsoft Edge или Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="d7000-106">As an Office 365 global administrator, you can configure Outlook on the web to deliver _lean popouts_, a smaller, less memory-intensive version of certain email messages in Microsoft Edge or Internet Explorer.</span></span> <span data-ttu-id="d7000-107">При настройке нежирных всплывающих Outlook в Интернете загружаются отрисовки серверных компонентов, которые оптимизируют производительность.</span><span class="sxs-lookup"><span data-stu-id="d7000-107">When lean popouts are configured for Outlook on the web, server-side rendered components are loaded that optimize performance.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d7000-108">По данным на март 2018 г., постные всплывающие сообщения недоступны для сообщений, которые указывают ограничения прав на использование, такие как управление правами на информацию (IRM).</span><span class="sxs-lookup"><span data-stu-id="d7000-108">As of March 2018, lean popouts are not available for messages that specify usage rights restrictions, such as Information Rights Management (IRM).</span></span>
  
<span data-ttu-id="d7000-109">Эти функции будут продолжать работать в главном окне, но недоступны в постных всплывающих окнах:</span><span class="sxs-lookup"><span data-stu-id="d7000-109">These features will continue to work in the main window but are not available in lean popouts:</span></span>
  
- <span data-ttu-id="d7000-110">Надстройки Outlook</span><span class="sxs-lookup"><span data-stu-id="d7000-110">Outlook add-ins</span></span>
  
- <span data-ttu-id="d7000-111">Skype для бизнеса присутствия</span><span class="sxs-lookup"><span data-stu-id="d7000-111">Skype for Business presence</span></span>
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a><span data-ttu-id="d7000-112">Настройка постных всплывающих окантовок для всех пользователей в Office 365 организации</span><span class="sxs-lookup"><span data-stu-id="d7000-112">To configure lean popouts for all users within your Office 365 organization</span></span>
  
1. <span data-ttu-id="d7000-113">[Подключение использовать Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="d7000-113">[Connect to Exchange Online Using Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
  
2. <span data-ttu-id="d7000-114">Выполните [набор-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) с параметром LeanPopoutEnabled следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d7000-114">Run the [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) cmdlet with the LeanPopoutEnabled parameter as follows:</span></span>

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  <span data-ttu-id="d7000-115">Например, чтобы включить нежирные всплывающие окантовки для всех пользователей в организации:</span><span class="sxs-lookup"><span data-stu-id="d7000-115">For example, to enable lean popouts for all users in your organization:</span></span>
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  <span data-ttu-id="d7000-116">Отключение постных всплывающих отключений для всех пользователей в организации:</span><span class="sxs-lookup"><span data-stu-id="d7000-116">To disable lean popouts for all users in your organization:</span></span>

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```