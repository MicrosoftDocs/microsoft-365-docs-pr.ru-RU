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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: 'Сведения о том, как включить или отключить функцию "несрочные" для всех или определенных пользователей в Организации с помощью Exchange PowerShell. '
ms.openlocfilehash: 6ba1e3f2b6a8a516a2b55267ab22fb43613350e0
ms.sourcegitcommit: 83f980927728bc080f97a3e6dc70dc305f3df841
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "44053840"
---
# <a name="configure-clutter-for-your-organization"></a><span data-ttu-id="3aaf2-103">Настройка функции 'Несрочные' для организации</span><span class="sxs-lookup"><span data-stu-id="3aaf2-103">Configure Clutter for your organization</span></span>

> [!TIP]
> <span data-ttu-id="3aaf2-104">[Сортировка папки "Входящие"](../setup/configure-focused-inbox.md) предполагает замену несрочных сообщений.</span><span class="sxs-lookup"><span data-stu-id="3aaf2-104">[Focused Inbox](../setup/configure-focused-inbox.md) is going to replace Clutter.</span></span> <span data-ttu-id="3aaf2-105">Дополнительные сведения: [обновление в статье Сортировка почты и планов для несрочных сообщений](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span><span class="sxs-lookup"><span data-stu-id="3aaf2-105">Learn more: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span></span>
  
<span data-ttu-id="3aaf2-106">Администратору может потребоваться управлять функцией "несрочные" в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3aaf2-106">As an admin, you may have to manage the Clutter feature in Microsoft 365.</span></span> <span data-ttu-id="3aaf2-107">Чтобы включить или отключить эту функцию для пользователей организации, используйте Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3aaf2-107">To turn the Clutter feature on/off for users in your organization, you must use Exchange PowerShell.</span></span> <span data-ttu-id="3aaf2-108">(Пользователи могут включать и отключать эту функцию, следуя инструкциям в статье [Отключение и включение функции "Несрочные" в Outlook](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx).)</span><span class="sxs-lookup"><span data-stu-id="3aaf2-108">(Individuals can turn it on/off using these instructions: [Turn off/on Clutter in Outlook](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx).)</span></span> 
  
<span data-ttu-id="3aaf2-109">Ознакомьтесь с [использованием PowerShell с Exchange Online](https://go.microsoft.com/fwlink/?LinkID=402831) и [подключитесь к Exchange Online PowerShell, чтобы](https://go.microsoft.com/fwlink/?LinkID=722415) узнать больше об использовании Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3aaf2-109">Check out [Using PowerShell with Exchange Online](https://go.microsoft.com/fwlink/?LinkID=402831) and [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?LinkID=722415) for details on using Exchange PowerShell.</span></span> <span data-ttu-id="3aaf2-110">Необходимо иметь учетную запись, которая имеет по крайней мере роль администратора службы Exchange и возможность подключения к Exchange Online с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3aaf2-110">You need to have an account that has at least the Exchange Service administrator role and the ability to connect to Exchange Online with PowerShell.</span></span> 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a><span data-ttu-id="3aaf2-111">Включение функции "Ненужные" с помощью Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="3aaf2-111">Turn Clutter on using Exchange PowerShell</span></span>

<span data-ttu-id="3aaf2-p104">Вы можете включить функцию "Ненужные" вручную для почтового ящика, выполнив командлет [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446). Вы также можете просматривать параметры функции "Ненужные" для почтовых ящиков в вашей организации с помощью командлета [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759).</span><span class="sxs-lookup"><span data-stu-id="3aaf2-p104">You can enable Clutter manually for a mailbox by running the [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet. You can also view Clutter settings for mailboxes in your organization by running the [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet.</span></span> 
  
<span data-ttu-id="3aaf2-114">Включение функции "Ненужные" для одного пользователя (Allie Bellew)</span><span class="sxs-lookup"><span data-stu-id="3aaf2-114">Turn on Clutter for a single user named Allie Bellew</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a><span data-ttu-id="3aaf2-115">Отключение функции "Ненужные" с помощью Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="3aaf2-115">Turn Clutter off using Exchange PowerShell</span></span>

<span data-ttu-id="3aaf2-p105">Вы можете отключить функцию "Ненужные" вручную для почтового ящика, выполнив командлет [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446). Вы также можете просматривать параметры функции **Ненужные** для почтовых ящиков в вашей организации с помощью командлета [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759).</span><span class="sxs-lookup"><span data-stu-id="3aaf2-p105">You can disable Clutter manually for a mailbox by running the [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet. You can also view **Clutter** settings for mailboxes in your organization by running the [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet.</span></span> 
  
<span data-ttu-id="3aaf2-118">Отключение функции "Ненужные" для одного пользователя (Allie Bellew)</span><span class="sxs-lookup"><span data-stu-id="3aaf2-118">Turn off Clutter for a single user named Allie Bellew:</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

<span data-ttu-id="3aaf2-119">Если вы использовали PowerShell для массового создания пользователей, вам потребуется выполнить командлет [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) для почтового ящика каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="3aaf2-119">If you use PowerShell to bulk create your users, then you'll need to run [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) against each user's mailbox to manage Clutter.</span></span> 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a><span data-ttu-id="3aaf2-120">Отображение переключателя функции "Несрочные" для пользователей в Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="3aaf2-120">When does the Clutter on/off switch appear to users in Outlook on the web?</span></span>
<span data-ttu-id="3aaf2-121"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="3aaf2-121"><a name="bkmk_onoff"> </a></span></span>

<span data-ttu-id="3aaf2-122">Как администратор, вы можете повторно включить функцию "несрочные" с помощью Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3aaf2-122">As an admin, you can re-enable Clutter using Exchange PowerShell.</span></span> <span data-ttu-id="3aaf2-123">После этого функция "Сортировка почты" отключается, а функция "Несрочные" снова становится активной.</span><span class="sxs-lookup"><span data-stu-id="3aaf2-123">Once this is done, Focused Inbox will be turned off and Clutter will be active again.</span></span> 
  
 <span data-ttu-id="3aaf2-124">**Если вы используете Outlook в Интернете с подпиской на Microsoft 365 Business Premium, выполните следующие действия:**</span><span class="sxs-lookup"><span data-stu-id="3aaf2-124">**If you're using Outlook on the web with a Microsoft 365 Business Premium subscription:**</span></span>
  
- <span data-ttu-id="3aaf2-125">если у пользователя включена функция "Несрочные":</span><span class="sxs-lookup"><span data-stu-id="3aaf2-125">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="3aaf2-126">отображаются параметры функции "Несрочные";</span><span class="sxs-lookup"><span data-stu-id="3aaf2-126">Clutter settings appear</span></span>
    
- <span data-ttu-id="3aaf2-127">если у пользователя включена функция "Сортировка почты":</span><span class="sxs-lookup"><span data-stu-id="3aaf2-127">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="3aaf2-128">параметры функции "Несрочные" не отображаются;</span><span class="sxs-lookup"><span data-stu-id="3aaf2-128">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="3aaf2-129">если отключены обе функции ("Несрочные" и "Сортировка почты"):</span><span class="sxs-lookup"><span data-stu-id="3aaf2-129">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="3aaf2-130">в параметрах почты пользователя отображаются параметры функций "Несрочные" и "Сортировка почты".</span><span class="sxs-lookup"><span data-stu-id="3aaf2-130">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
 <span data-ttu-id="3aaf2-131">**При использовании Outlook.com:**</span><span class="sxs-lookup"><span data-stu-id="3aaf2-131">**If you're using Outlook.com:**</span></span>
  
- <span data-ttu-id="3aaf2-132">если у пользователя включена функция "Несрочные":</span><span class="sxs-lookup"><span data-stu-id="3aaf2-132">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="3aaf2-133">отображаются параметры функции "Несрочные";</span><span class="sxs-lookup"><span data-stu-id="3aaf2-133">Clutter settings appear</span></span>
    
- <span data-ttu-id="3aaf2-134">если у пользователя включена функция "Сортировка почты":</span><span class="sxs-lookup"><span data-stu-id="3aaf2-134">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="3aaf2-135">параметры функции "Несрочные" не отображаются;</span><span class="sxs-lookup"><span data-stu-id="3aaf2-135">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="3aaf2-136">если отключены обе функции ("Несрочные" и "Сортировка почты"):</span><span class="sxs-lookup"><span data-stu-id="3aaf2-136">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="3aaf2-137">в параметрах почты пользователя отображаются параметры функций "Несрочные" и "Сортировка почты";</span><span class="sxs-lookup"><span data-stu-id="3aaf2-137">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
- <span data-ttu-id="3aaf2-138">если пользователь включил функцию "Сортировка почты" раньше:</span><span class="sxs-lookup"><span data-stu-id="3aaf2-138">If user enabled Focused Inbox at some point in the past:</span></span>
    
  - <span data-ttu-id="3aaf2-139">параметры функции "Несрочные" никогда не будут отображаться;</span><span class="sxs-lookup"><span data-stu-id="3aaf2-139">Clutter settings will never appear</span></span>
    
    <span data-ttu-id="3aaf2-140">в противном случае:</span><span class="sxs-lookup"><span data-stu-id="3aaf2-140">Otherwise,</span></span> 
    
  - <span data-ttu-id="3aaf2-141">параметры функции "Несрочные" отображаются.</span><span class="sxs-lookup"><span data-stu-id="3aaf2-141">Clutter settings will appear</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="3aaf2-142">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="3aaf2-142">Related articles</span></span>
<span data-ttu-id="3aaf2-143"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="3aaf2-143"><a name="bkmk_onoff"> </a></span></span>

[<span data-ttu-id="3aaf2-144">Использование функции "Несрочные" для сортировки сообщений с низким приоритетом в Outlook</span><span class="sxs-lookup"><span data-stu-id="3aaf2-144">Use Clutter to sort low priority messages in Outlook</span></span>](https://support.office.com/article/use-clutter-to-sort-low-priority-messages-in-outlook-7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0)
    
[<span data-ttu-id="3aaf2-145">Использование функции "несрочные" для сортировки сообщений с небольшим приоритетом в OWA</span><span class="sxs-lookup"><span data-stu-id="3aaf2-145">Use Clutter to sort low priority messages in OWA</span></span>](https://support.office.com/article/fe4d64ca-bf73-48f1-91b4-9a659e008bce.aspx)
    
[<span data-ttu-id="3aaf2-146">Отключение функции "Несрочные" в Outlook</span><span class="sxs-lookup"><span data-stu-id="3aaf2-146">Turn off Clutter in Outlook</span></span>](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx)
    

