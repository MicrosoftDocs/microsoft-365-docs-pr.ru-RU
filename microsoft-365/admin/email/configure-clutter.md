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
description: 'Узнайте, как включить или отключить функцию "Нехотяй" для всех или отдельных пользователей в организации с помощью Exchange PowerShell. '
ms.openlocfilehash: 67267b0865dfcfd6c0ba66d59ce1d0d111d59325
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780281"
---
# <a name="configure-clutter-for-your-organization"></a><span data-ttu-id="a4426-103">Настройка функции 'Несрочные' для организации</span><span class="sxs-lookup"><span data-stu-id="a4426-103">Configure Clutter for your organization</span></span>

> [!TIP]
> <span data-ttu-id="a4426-104">[Focused Inbox](../setup/configure-focused-inbox.md) is going to replace Clutter.</span><span class="sxs-lookup"><span data-stu-id="a4426-104">[Focused Inbox](../setup/configure-focused-inbox.md) is going to replace Clutter.</span></span> <span data-ttu-id="a4426-105">Подробнее: [обновление отсорт почты и планы для "Нехожих"](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span><span class="sxs-lookup"><span data-stu-id="a4426-105">Learn more: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span></span>
  
<span data-ttu-id="a4426-106">Администратору может потребоваться управлять функцией "Нехотяй" в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a4426-106">As an admin, you may have to manage the Clutter feature in Microsoft 365.</span></span> <span data-ttu-id="a4426-107">Чтобы включить или отключить эту функцию для пользователей организации, используйте Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a4426-107">To turn the Clutter feature on/off for users in your organization, you must use Exchange PowerShell.</span></span> <span data-ttu-id="a4426-108">(Отдельные люди могут включить или отключить его, выключив или отключив эту инструкцию: "Отключить или [включить нехожим" в Outlook.](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)</span><span class="sxs-lookup"><span data-stu-id="a4426-108">(Individuals can turn it on/off using these instructions: [Turn off/on Clutter in Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c).</span></span>
  
<span data-ttu-id="a4426-109">Подробные сведения об использовании [Exchange PowerShell](https://go.microsoft.com/fwlink/?LinkID=402831) можно найти на веб-сайте PowerShell с Exchange Online и Exchange [Online PowerShell.](https://go.microsoft.com/fwlink/?LinkID=722415)</span><span class="sxs-lookup"><span data-stu-id="a4426-109">Check out [Using PowerShell with Exchange Online](https://go.microsoft.com/fwlink/?LinkID=402831) and [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?LinkID=722415) for details on using Exchange PowerShell.</span></span> <span data-ttu-id="a4426-110">Необходимо иметь учетную запись, которая имеет по крайней мере роль администратора службы Exchange и возможность подключения к Exchange Online с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a4426-110">You need to have an account that has at least the Exchange Service administrator role and the ability to connect to Exchange Online with PowerShell.</span></span> 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a><span data-ttu-id="a4426-111">Включение функции "Ненужные" с помощью Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="a4426-111">Turn Clutter on using Exchange PowerShell</span></span>

<span data-ttu-id="a4426-p104">Вы можете включить функцию "Ненужные" вручную для почтового ящика, выполнив командлет [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446). Вы также можете просматривать параметры функции "Ненужные" для почтовых ящиков в вашей организации с помощью командлета [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759).</span><span class="sxs-lookup"><span data-stu-id="a4426-p104">You can enable Clutter manually for a mailbox by running the [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet. You can also view Clutter settings for mailboxes in your organization by running the [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet.</span></span> 
  
<span data-ttu-id="a4426-114">Включение функции "Ненужные" для одного пользователя (Allie Bellew)</span><span class="sxs-lookup"><span data-stu-id="a4426-114">Turn on Clutter for a single user named Allie Bellew</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a><span data-ttu-id="a4426-115">Отключение функции "Ненужные" с помощью Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="a4426-115">Turn Clutter off using Exchange PowerShell</span></span>

<span data-ttu-id="a4426-p105">Вы можете отключить функцию "Ненужные" вручную для почтового ящика, выполнив командлет [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446). Вы также можете просматривать параметры функции **Ненужные** для почтовых ящиков в вашей организации с помощью командлета [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759).</span><span class="sxs-lookup"><span data-stu-id="a4426-p105">You can disable Clutter manually for a mailbox by running the [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet. You can also view **Clutter** settings for mailboxes in your organization by running the [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet.</span></span> 
  
<span data-ttu-id="a4426-118">Отключение функции "Ненужные" для одного пользователя (Allie Bellew)</span><span class="sxs-lookup"><span data-stu-id="a4426-118">Turn off Clutter for a single user named Allie Bellew:</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

<span data-ttu-id="a4426-119">Если вы использовали PowerShell для массового создания пользователей, вам потребуется выполнить командлет [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) для почтового ящика каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="a4426-119">If you use PowerShell to bulk create your users, then you'll need to run [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) against each user's mailbox to manage Clutter.</span></span> 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a><span data-ttu-id="a4426-120">Отображение переключателя функции "Несрочные" для пользователей в Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="a4426-120">When does the Clutter on/off switch appear to users in Outlook on the web?</span></span>
<span data-ttu-id="a4426-121"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="a4426-121"><a name="bkmk_onoff"> </a></span></span>

<span data-ttu-id="a4426-122">Как администратор вы можете повторно включить эту возможность с помощью Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a4426-122">As an admin, you can re-enable Clutter using Exchange PowerShell.</span></span> <span data-ttu-id="a4426-123">После этого функция "Сортировка почты" отключается, а функция "Несрочные" снова становится активной.</span><span class="sxs-lookup"><span data-stu-id="a4426-123">Once this is done, Focused Inbox will be turned off and Clutter will be active again.</span></span> 
  
 <span data-ttu-id="a4426-124">**Если вы используете Outlook в Интернете с подпиской microsoft 365 бизнес премиум:**</span><span class="sxs-lookup"><span data-stu-id="a4426-124">**If you're using Outlook on the web with a Microsoft 365 Business Premium subscription:**</span></span>
  
- <span data-ttu-id="a4426-125">если у пользователя включена функция "Несрочные":</span><span class="sxs-lookup"><span data-stu-id="a4426-125">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="a4426-126">отображаются параметры функции "Несрочные";</span><span class="sxs-lookup"><span data-stu-id="a4426-126">Clutter settings appear</span></span>
    
- <span data-ttu-id="a4426-127">если у пользователя включена функция "Сортировка почты":</span><span class="sxs-lookup"><span data-stu-id="a4426-127">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="a4426-128">параметры функции "Несрочные" не отображаются;</span><span class="sxs-lookup"><span data-stu-id="a4426-128">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="a4426-129">если отключены обе функции ("Несрочные" и "Сортировка почты"):</span><span class="sxs-lookup"><span data-stu-id="a4426-129">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="a4426-130">в параметрах почты пользователя отображаются параметры функций "Несрочные" и "Сортировка почты".</span><span class="sxs-lookup"><span data-stu-id="a4426-130">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
 <span data-ttu-id="a4426-131">**При использовании Outlook.com:**</span><span class="sxs-lookup"><span data-stu-id="a4426-131">**If you're using Outlook.com:**</span></span>
  
- <span data-ttu-id="a4426-132">если у пользователя включена функция "Несрочные":</span><span class="sxs-lookup"><span data-stu-id="a4426-132">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="a4426-133">отображаются параметры функции "Несрочные";</span><span class="sxs-lookup"><span data-stu-id="a4426-133">Clutter settings appear</span></span>
    
- <span data-ttu-id="a4426-134">если у пользователя включена функция "Сортировка почты":</span><span class="sxs-lookup"><span data-stu-id="a4426-134">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="a4426-135">параметры функции "Несрочные" не отображаются;</span><span class="sxs-lookup"><span data-stu-id="a4426-135">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="a4426-136">если отключены обе функции ("Несрочные" и "Сортировка почты"):</span><span class="sxs-lookup"><span data-stu-id="a4426-136">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="a4426-137">в параметрах почты пользователя отображаются параметры функций "Несрочные" и "Сортировка почты";</span><span class="sxs-lookup"><span data-stu-id="a4426-137">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
- <span data-ttu-id="a4426-138">если пользователь включил функцию "Сортировка почты" раньше:</span><span class="sxs-lookup"><span data-stu-id="a4426-138">If user enabled Focused Inbox at some point in the past:</span></span>
    
  - <span data-ttu-id="a4426-139">параметры функции "Несрочные" никогда не будут отображаться;</span><span class="sxs-lookup"><span data-stu-id="a4426-139">Clutter settings will never appear</span></span>
    
    <span data-ttu-id="a4426-140">в противном случае:</span><span class="sxs-lookup"><span data-stu-id="a4426-140">Otherwise,</span></span> 
    
  - <span data-ttu-id="a4426-141">параметры функции "Несрочные" отображаются.</span><span class="sxs-lookup"><span data-stu-id="a4426-141">Clutter settings will appear</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="a4426-142">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="a4426-142">Related articles</span></span>
<span data-ttu-id="a4426-143"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="a4426-143"><a name="bkmk_onoff"> </a></span></span>

[<span data-ttu-id="a4426-144">Использование функции "Несрочные" для сортировки сообщений с низким приоритетом в Outlook</span><span class="sxs-lookup"><span data-stu-id="a4426-144">Use Clutter to sort low priority messages in Outlook</span></span>](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0)
    
[<span data-ttu-id="a4426-145">Использование "Нехват" для сортировки сообщений с низким приоритетом в OWA</span><span class="sxs-lookup"><span data-stu-id="a4426-145">Use Clutter to sort low priority messages in OWA</span></span>](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce)
    
[<span data-ttu-id="a4426-146">Отключение функции "Несрочные" в Outlook</span><span class="sxs-lookup"><span data-stu-id="a4426-146">Turn off Clutter in Outlook</span></span>](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)
    

