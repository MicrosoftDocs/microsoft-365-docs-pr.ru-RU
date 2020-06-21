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
description: 'Сведения о том, как включить или отключить функцию "несрочные" для всех или определенных пользователей в Организации с помощью Exchange PowerShell. '
ms.openlocfilehash: 67267b0865dfcfd6c0ba66d59ce1d0d111d59325
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780281"
---
# <a name="configure-clutter-for-your-organization"></a><span data-ttu-id="b203d-103">Настройка функции 'Несрочные' для организации</span><span class="sxs-lookup"><span data-stu-id="b203d-103">Configure Clutter for your organization</span></span>

> [!TIP]
> <span data-ttu-id="b203d-104">[Сортировка папки "Входящие"](../setup/configure-focused-inbox.md) предполагает замену несрочных сообщений.</span><span class="sxs-lookup"><span data-stu-id="b203d-104">[Focused Inbox](../setup/configure-focused-inbox.md) is going to replace Clutter.</span></span> <span data-ttu-id="b203d-105">Дополнительные сведения: [обновление в статье Сортировка почты и планов для несрочных сообщений](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span><span class="sxs-lookup"><span data-stu-id="b203d-105">Learn more: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span></span>
  
<span data-ttu-id="b203d-106">Администратору может потребоваться управлять функцией "несрочные" в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b203d-106">As an admin, you may have to manage the Clutter feature in Microsoft 365.</span></span> <span data-ttu-id="b203d-107">Чтобы включить или отключить эту функцию для пользователей организации, используйте Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b203d-107">To turn the Clutter feature on/off for users in your organization, you must use Exchange PowerShell.</span></span> <span data-ttu-id="b203d-108">(Пользователи могут включать и отключать эту функцию с помощью следующих инструкций: отключение [/Включение функции "несрочные" в Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c).</span><span class="sxs-lookup"><span data-stu-id="b203d-108">(Individuals can turn it on/off using these instructions: [Turn off/on Clutter in Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c).</span></span>
  
<span data-ttu-id="b203d-109">Ознакомьтесь с [использованием PowerShell с Exchange Online](https://go.microsoft.com/fwlink/?LinkID=402831) и [подключитесь к Exchange Online PowerShell, чтобы](https://go.microsoft.com/fwlink/?LinkID=722415) узнать больше об использовании Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b203d-109">Check out [Using PowerShell with Exchange Online](https://go.microsoft.com/fwlink/?LinkID=402831) and [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?LinkID=722415) for details on using Exchange PowerShell.</span></span> <span data-ttu-id="b203d-110">Необходимо иметь учетную запись, которая имеет по крайней мере роль администратора службы Exchange и возможность подключения к Exchange Online с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b203d-110">You need to have an account that has at least the Exchange Service administrator role and the ability to connect to Exchange Online with PowerShell.</span></span> 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a><span data-ttu-id="b203d-111">Включение функции "Ненужные" с помощью Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="b203d-111">Turn Clutter on using Exchange PowerShell</span></span>

<span data-ttu-id="b203d-112">You can enable Clutter manually for a mailbox by running the [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b203d-112">You can enable Clutter manually for a mailbox by running the [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet.</span></span> <span data-ttu-id="b203d-113">You can also view Clutter settings for mailboxes in your organization by running the [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b203d-113">You can also view Clutter settings for mailboxes in your organization by running the [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet.</span></span> 
  
<span data-ttu-id="b203d-114">Включение функции "Ненужные" для одного пользователя (Allie Bellew)</span><span class="sxs-lookup"><span data-stu-id="b203d-114">Turn on Clutter for a single user named Allie Bellew</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a><span data-ttu-id="b203d-115">Отключение функции "Ненужные" с помощью Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="b203d-115">Turn Clutter off using Exchange PowerShell</span></span>

<span data-ttu-id="b203d-116">You can disable Clutter manually for a mailbox by running the [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b203d-116">You can disable Clutter manually for a mailbox by running the [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet.</span></span> <span data-ttu-id="b203d-117">You can also view **Clutter** settings for mailboxes in your organization by running the [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b203d-117">You can also view **Clutter** settings for mailboxes in your organization by running the [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet.</span></span> 
  
<span data-ttu-id="b203d-118">Отключение функции "Ненужные" для одного пользователя (Allie Bellew)</span><span class="sxs-lookup"><span data-stu-id="b203d-118">Turn off Clutter for a single user named Allie Bellew:</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

<span data-ttu-id="b203d-119">Если вы использовали PowerShell для массового создания пользователей, вам потребуется выполнить командлет [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) для почтового ящика каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="b203d-119">If you use PowerShell to bulk create your users, then you'll need to run [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) against each user's mailbox to manage Clutter.</span></span> 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a><span data-ttu-id="b203d-120">Отображение переключателя функции "Несрочные" для пользователей в Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="b203d-120">When does the Clutter on/off switch appear to users in Outlook on the web?</span></span>
<span data-ttu-id="b203d-121"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="b203d-121"><a name="bkmk_onoff"> </a></span></span>

<span data-ttu-id="b203d-122">Как администратор, вы можете повторно включить функцию "несрочные" с помощью Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b203d-122">As an admin, you can re-enable Clutter using Exchange PowerShell.</span></span> <span data-ttu-id="b203d-123">После этого функция "Сортировка почты" отключается, а функция "Несрочные" снова становится активной.</span><span class="sxs-lookup"><span data-stu-id="b203d-123">Once this is done, Focused Inbox will be turned off and Clutter will be active again.</span></span> 
  
 <span data-ttu-id="b203d-124">**Если вы используете Outlook в Интернете с подпиской на Microsoft 365 Business Premium, выполните следующие действия:**</span><span class="sxs-lookup"><span data-stu-id="b203d-124">**If you're using Outlook on the web with a Microsoft 365 Business Premium subscription:**</span></span>
  
- <span data-ttu-id="b203d-125">если у пользователя включена функция "Несрочные":</span><span class="sxs-lookup"><span data-stu-id="b203d-125">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="b203d-126">отображаются параметры функции "Несрочные";</span><span class="sxs-lookup"><span data-stu-id="b203d-126">Clutter settings appear</span></span>
    
- <span data-ttu-id="b203d-127">если у пользователя включена функция "Сортировка почты":</span><span class="sxs-lookup"><span data-stu-id="b203d-127">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="b203d-128">параметры функции "Несрочные" не отображаются;</span><span class="sxs-lookup"><span data-stu-id="b203d-128">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="b203d-129">если отключены обе функции ("Несрочные" и "Сортировка почты"):</span><span class="sxs-lookup"><span data-stu-id="b203d-129">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="b203d-130">в параметрах почты пользователя отображаются параметры функций "Несрочные" и "Сортировка почты".</span><span class="sxs-lookup"><span data-stu-id="b203d-130">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
 <span data-ttu-id="b203d-131">**При использовании Outlook.com:**</span><span class="sxs-lookup"><span data-stu-id="b203d-131">**If you're using Outlook.com:**</span></span>
  
- <span data-ttu-id="b203d-132">если у пользователя включена функция "Несрочные":</span><span class="sxs-lookup"><span data-stu-id="b203d-132">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="b203d-133">отображаются параметры функции "Несрочные";</span><span class="sxs-lookup"><span data-stu-id="b203d-133">Clutter settings appear</span></span>
    
- <span data-ttu-id="b203d-134">если у пользователя включена функция "Сортировка почты":</span><span class="sxs-lookup"><span data-stu-id="b203d-134">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="b203d-135">параметры функции "Несрочные" не отображаются;</span><span class="sxs-lookup"><span data-stu-id="b203d-135">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="b203d-136">если отключены обе функции ("Несрочные" и "Сортировка почты"):</span><span class="sxs-lookup"><span data-stu-id="b203d-136">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="b203d-137">в параметрах почты пользователя отображаются параметры функций "Несрочные" и "Сортировка почты";</span><span class="sxs-lookup"><span data-stu-id="b203d-137">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
- <span data-ttu-id="b203d-138">если пользователь включил функцию "Сортировка почты" раньше:</span><span class="sxs-lookup"><span data-stu-id="b203d-138">If user enabled Focused Inbox at some point in the past:</span></span>
    
  - <span data-ttu-id="b203d-139">параметры функции "Несрочные" никогда не будут отображаться;</span><span class="sxs-lookup"><span data-stu-id="b203d-139">Clutter settings will never appear</span></span>
    
    <span data-ttu-id="b203d-140">в противном случае:</span><span class="sxs-lookup"><span data-stu-id="b203d-140">Otherwise,</span></span> 
    
  - <span data-ttu-id="b203d-141">параметры функции "Несрочные" отображаются.</span><span class="sxs-lookup"><span data-stu-id="b203d-141">Clutter settings will appear</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="b203d-142">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="b203d-142">Related articles</span></span>
<span data-ttu-id="b203d-143"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="b203d-143"><a name="bkmk_onoff"> </a></span></span>

[<span data-ttu-id="b203d-144">Использование функции "Несрочные" для сортировки сообщений с низким приоритетом в Outlook</span><span class="sxs-lookup"><span data-stu-id="b203d-144">Use Clutter to sort low priority messages in Outlook</span></span>](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0)
    
[<span data-ttu-id="b203d-145">Использование функции "несрочные" для сортировки сообщений с небольшим приоритетом в OWA</span><span class="sxs-lookup"><span data-stu-id="b203d-145">Use Clutter to sort low priority messages in OWA</span></span>](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce)
    
[<span data-ttu-id="b203d-146">Отключение функции "Несрочные" в Outlook</span><span class="sxs-lookup"><span data-stu-id="b203d-146">Turn off Clutter in Outlook</span></span>](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)
    

