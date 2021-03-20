---
title: Настройка функции 'Несрочные' для организации
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: 'Узнайте, как включить или отключить функцию Clutter для всех или определенных пользователей в организации с помощью Exchange PowerShell. '
ms.openlocfilehash: ac68893bc0aeea5ab214698c54524921e2b1921d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915906"
---
# <a name="configure-clutter-for-your-organization"></a><span data-ttu-id="83623-103">Настройка функции 'Несрочные' для организации</span><span class="sxs-lookup"><span data-stu-id="83623-103">Configure Clutter for your organization</span></span>

> [!TIP]
> <span data-ttu-id="83623-104">[Сфокусированный почтовый ящик](../setup/configure-focused-inbox.md) заменит clutter.</span><span class="sxs-lookup"><span data-stu-id="83623-104">[Focused Inbox](../setup/configure-focused-inbox.md) is going to replace Clutter.</span></span> <span data-ttu-id="83623-105">Дополнительные новости. [Обновление по сфокусированным почтовым ящикам и нашим планам по помехам](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span><span class="sxs-lookup"><span data-stu-id="83623-105">Learn more: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span></span>
  
<span data-ttu-id="83623-106">Как администратору может потребоваться управлять функцией Clutter в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="83623-106">As an admin, you may have to manage the Clutter feature in Microsoft 365.</span></span> <span data-ttu-id="83623-107">Чтобы включить или отключить эту функцию для пользователей организации, используйте Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="83623-107">To turn the Clutter feature on/off for users in your organization, you must use Exchange PowerShell.</span></span> <span data-ttu-id="83623-108">(Физические лица могут включить и отключить его с помощью этих инструкций: [Выключите или нагромождение в Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c).</span><span class="sxs-lookup"><span data-stu-id="83623-108">(Individuals can turn it on/off using these instructions: [Turn off/on Clutter in Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c).</span></span>
  
<span data-ttu-id="83623-109">Сведения об [использовании PowerShell с Помощью PowerShell](/powershell/exchange/exchange-online-powershell) с Exchange Online и Подключение к Exchange Online [PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="83623-109">Check out [Using PowerShell with Exchange Online](/powershell/exchange/exchange-online-powershell) and [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) for details on using Exchange PowerShell.</span></span> <span data-ttu-id="83623-110">Необходимо иметь учетную запись, которая имеет хотя бы роль администратора службы Exchange и возможность подключения к Exchange Online с PowerShell.</span><span class="sxs-lookup"><span data-stu-id="83623-110">You need to have an account that has at least the Exchange Service administrator role and the ability to connect to Exchange Online with PowerShell.</span></span> 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a><span data-ttu-id="83623-111">Включение функции "Ненужные" с помощью Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="83623-111">Turn Clutter on using Exchange PowerShell</span></span>

<span data-ttu-id="83623-p104">Вы можете включить функцию "Ненужные" вручную для почтового ящика, выполнив командлет [Set-Clutter](/powershell/module/exchange/set-clutter). Вы также можете просматривать параметры функции "Ненужные" для почтовых ящиков в вашей организации с помощью командлета [Get-Clutter](/powershell/module/exchange/get-clutter).</span><span class="sxs-lookup"><span data-stu-id="83623-p104">You can enable Clutter manually for a mailbox by running the [Set-Clutter](/powershell/module/exchange/set-clutter) cmdlet. You can also view Clutter settings for mailboxes in your organization by running the [Get-Clutter](/powershell/module/exchange/get-clutter) cmdlet.</span></span> 
  
<span data-ttu-id="83623-114">Включение функции "Ненужные" для одного пользователя (Allie Bellew)</span><span class="sxs-lookup"><span data-stu-id="83623-114">Turn on Clutter for a single user named Allie Bellew</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a><span data-ttu-id="83623-115">Отключение функции "Ненужные" с помощью Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="83623-115">Turn Clutter off using Exchange PowerShell</span></span>

<span data-ttu-id="83623-p105">Вы можете отключить функцию "Ненужные" вручную для почтового ящика, выполнив командлет [Set-Clutter](/powershell/module/exchange/set-clutter). Вы также можете просматривать параметры функции **Ненужные** для почтовых ящиков в вашей организации с помощью командлета [Get-Clutter](/powershell/module/exchange/get-clutter).</span><span class="sxs-lookup"><span data-stu-id="83623-p105">You can disable Clutter manually for a mailbox by running the [Set-Clutter](/powershell/module/exchange/set-clutter) cmdlet. You can also view **Clutter** settings for mailboxes in your organization by running the [Get-Clutter](/powershell/module/exchange/get-clutter) cmdlet.</span></span> 
  
<span data-ttu-id="83623-118">Отключение функции "Ненужные" для одного пользователя (Allie Bellew)</span><span class="sxs-lookup"><span data-stu-id="83623-118">Turn off Clutter for a single user named Allie Bellew:</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

<span data-ttu-id="83623-119">Если вы использовали PowerShell для массового создания пользователей, вам потребуется выполнить командлет [Set-Clutter](/powershell/module/exchange/set-clutter) для почтового ящика каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="83623-119">If you use PowerShell to bulk create your users, then you'll need to run [Set-Clutter](/powershell/module/exchange/set-clutter) against each user's mailbox to manage Clutter.</span></span> 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a><span data-ttu-id="83623-120">Отображение переключателя функции "Несрочные" для пользователей в Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="83623-120">When does the Clutter on/off switch appear to users in Outlook on the web?</span></span>
<span data-ttu-id="83623-121"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="83623-121"><a name="bkmk_onoff"> </a></span></span>

<span data-ttu-id="83623-122">В качестве администратора можно повторно включить clutter с помощью Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="83623-122">As an admin, you can re-enable Clutter using Exchange PowerShell.</span></span> <span data-ttu-id="83623-123">После этого функция "Сортировка почты" отключается, а функция "Несрочные" снова становится активной.</span><span class="sxs-lookup"><span data-stu-id="83623-123">Once this is done, Focused Inbox will be turned off and Clutter will be active again.</span></span> 
  
 <span data-ttu-id="83623-124">**Если вы используете Outlook в Интернете с подпиской Microsoft 365 Бизнес Премиум:**</span><span class="sxs-lookup"><span data-stu-id="83623-124">**If you're using Outlook on the web with a Microsoft 365 Business Premium subscription:**</span></span>
  
- <span data-ttu-id="83623-125">если у пользователя включена функция "Несрочные":</span><span class="sxs-lookup"><span data-stu-id="83623-125">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="83623-126">отображаются параметры функции "Несрочные";</span><span class="sxs-lookup"><span data-stu-id="83623-126">Clutter settings appear</span></span>
    
- <span data-ttu-id="83623-127">если у пользователя включена функция "Сортировка почты":</span><span class="sxs-lookup"><span data-stu-id="83623-127">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="83623-128">параметры функции "Несрочные" не отображаются;</span><span class="sxs-lookup"><span data-stu-id="83623-128">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="83623-129">если отключены обе функции ("Несрочные" и "Сортировка почты"):</span><span class="sxs-lookup"><span data-stu-id="83623-129">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="83623-130">в параметрах почты пользователя отображаются параметры функций "Несрочные" и "Сортировка почты".</span><span class="sxs-lookup"><span data-stu-id="83623-130">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
 <span data-ttu-id="83623-131">**При использовании Outlook.com:**</span><span class="sxs-lookup"><span data-stu-id="83623-131">**If you're using Outlook.com:**</span></span>
  
- <span data-ttu-id="83623-132">если у пользователя включена функция "Несрочные":</span><span class="sxs-lookup"><span data-stu-id="83623-132">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="83623-133">отображаются параметры функции "Несрочные";</span><span class="sxs-lookup"><span data-stu-id="83623-133">Clutter settings appear</span></span>
    
- <span data-ttu-id="83623-134">если у пользователя включена функция "Сортировка почты":</span><span class="sxs-lookup"><span data-stu-id="83623-134">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="83623-135">параметры функции "Несрочные" не отображаются;</span><span class="sxs-lookup"><span data-stu-id="83623-135">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="83623-136">если отключены обе функции ("Несрочные" и "Сортировка почты"):</span><span class="sxs-lookup"><span data-stu-id="83623-136">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="83623-137">в параметрах почты пользователя отображаются параметры функций "Несрочные" и "Сортировка почты";</span><span class="sxs-lookup"><span data-stu-id="83623-137">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
- <span data-ttu-id="83623-138">если пользователь включил функцию "Сортировка почты" раньше:</span><span class="sxs-lookup"><span data-stu-id="83623-138">If user enabled Focused Inbox at some point in the past:</span></span>
    
  - <span data-ttu-id="83623-139">параметры функции "Несрочные" никогда не будут отображаться;</span><span class="sxs-lookup"><span data-stu-id="83623-139">Clutter settings will never appear</span></span>
    
    <span data-ttu-id="83623-140">в противном случае:</span><span class="sxs-lookup"><span data-stu-id="83623-140">Otherwise,</span></span> 
    
  - <span data-ttu-id="83623-141">параметры функции "Несрочные" отображаются.</span><span class="sxs-lookup"><span data-stu-id="83623-141">Clutter settings will appear</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="83623-142">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="83623-142">Related articles</span></span>
<span data-ttu-id="83623-143"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="83623-143"><a name="bkmk_onoff"> </a></span></span>

[<span data-ttu-id="83623-144">Использование функции "Несрочные" для сортировки сообщений с низким приоритетом в Outlook</span><span class="sxs-lookup"><span data-stu-id="83623-144">Use Clutter to sort low priority messages in Outlook</span></span>](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0)
    
[<span data-ttu-id="83623-145">Использование clutter для сортировки сообщений с низким приоритетом в OWA</span><span class="sxs-lookup"><span data-stu-id="83623-145">Use Clutter to sort low priority messages in OWA</span></span>](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce)
    
[<span data-ttu-id="83623-146">Отключение функции "Несрочные" в Outlook</span><span class="sxs-lookup"><span data-stu-id="83623-146">Turn off Clutter in Outlook</span></span>](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)
