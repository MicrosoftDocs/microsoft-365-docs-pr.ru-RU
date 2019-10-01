---
title: Включение и отключение поиска в журнале аудита Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
description: Вы можете включить функцию поиска журнала аудита в центре безопасности & соответствия требованиям. Если вы передумали, вы можете включить его в любое время. Если поиск в журнале аудита отключен, администраторы не могут выполнять поиск действий пользователей и администраторов в журнале аудита Office 365 в Организации.
ms.openlocfilehash: 83ef355c4acd5e0af4fd7ffbf13157307bcac930
ms.sourcegitcommit: 53d848ebd4799b285d0f67c49b0aa24c88bd0e23
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "37334249"
---
# <a name="turn-office-365-audit-log-search-on-or-off"></a><span data-ttu-id="8b6ab-105">Включение и отключение поиска в журнале аудита Office 365</span><span class="sxs-lookup"><span data-stu-id="8b6ab-105">Turn Office 365 audit log search on or off</span></span>

<span data-ttu-id="8b6ab-106">Перед началом поиска в журнале аудита Office 365 вы (или другой администратор) должны включить ведение журнала аудита.</span><span class="sxs-lookup"><span data-stu-id="8b6ab-106">You (or another admin) must turn on audit logging before you can start searching the Office 365 audit log.</span></span> <span data-ttu-id="8b6ab-107">Когда включен Поиск в журнале аудита в центре безопасности & соответствия требованиям, действия пользователей и администраторов из вашей организации записываются в журнал аудита и хранятся в течение 90 дней.</span><span class="sxs-lookup"><span data-stu-id="8b6ab-107">When audit log search in the Security & Compliance Center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days.</span></span> <span data-ttu-id="8b6ab-108">Однако Организация может не заносить и хранить данные журнала аудита.</span><span class="sxs-lookup"><span data-stu-id="8b6ab-108">However, your organization may not want to record and retain audit log data.</span></span> <span data-ttu-id="8b6ab-109">Кроме того, для доступа к данным аудита можно использовать сторонние сведения о безопасности и приложение управления событиями (SIEM).</span><span class="sxs-lookup"><span data-stu-id="8b6ab-109">Or you may be using a third-party security information and event management (SIEM) application to access your auditing data.</span></span> <span data-ttu-id="8b6ab-110">В таких случаях глобальный администратор может отключить поиск в журнале аудита в Office 365.</span><span class="sxs-lookup"><span data-stu-id="8b6ab-110">In those cases, a global admin can turn off audit log search in Office 365.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="8b6ab-111">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="8b6ab-111">Before you begin</span></span>

- <span data-ttu-id="8b6ab-112">Роль журналов аудита в Exchange Online должна быть назначена для включения или отключения поиска журнала аудита в организации Office 365.</span><span class="sxs-lookup"><span data-stu-id="8b6ab-112">You have to be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Office 365 organization.</span></span> <span data-ttu-id="8b6ab-113">По умолчанию эта роль назначается группам ролей "Управление соответствием требованиям" и "Управление организацией" на странице " **разрешения** " в центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="8b6ab-113">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="8b6ab-114">Глобальные администраторы в Office 365 являются участниками группы ролей Управление организацией в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8b6ab-114">Global admins in Office 365 are members of the Organization Management role group in Exchange Online.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="8b6ab-115">Пользователям необходимо назначить разрешения в Exchange Online, чтобы включить или отключить поиск в журнале аудита.</span><span class="sxs-lookup"><span data-stu-id="8b6ab-115">Users have to be assigned permissions in Exchange Online to turn audit log search on or off.</span></span> <span data-ttu-id="8b6ab-116">Если вы назначили пользователям роль "журналы аудита" на странице " **разрешения** " центра безопасности & соответствия требованиям, они не смогут включать или отключать поиск в журнале аудита.</span><span class="sxs-lookup"><span data-stu-id="8b6ab-116">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn audit log search on or off.</span></span> <span data-ttu-id="8b6ab-117">Это вызвано тем, что базовый командлет является командлетом Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8b6ab-117">This is because the underlying cmdlet is an Exchange Online cmdlet.</span></span> 
  
- <span data-ttu-id="8b6ab-118">Если вы отключите Поиск журнала аудита в Office 365, вы не сможете использовать API действий управления Office 365 для доступа к данным аудита в Организации.</span><span class="sxs-lookup"><span data-stu-id="8b6ab-118">If you turn off audit log search in Office 365, you can't use the Office 365 Management Activity API to access auditing data for your organization.</span></span> <span data-ttu-id="8b6ab-119">Отключение поиска в журнале аудита с помощью действий, описанных в этой статье, означает, что при поиске в журнале аудита с помощью центра безопасности & соответствия требованиям или при запуске командлета **Search-UnifiedAuditLog** в Exchange Online PowerShell не будет возвращено никаких результатов .</span><span class="sxs-lookup"><span data-stu-id="8b6ab-119">Turning off audit log search by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="8b6ab-120">Это также означает, что журналы аудита не будут доступны через API действий управления Office 365.</span><span class="sxs-lookup"><span data-stu-id="8b6ab-120">This also means that your audit logs won't be available through the Office 365 Management Activity API.</span></span>  
    
- <span data-ttu-id="8b6ab-121">Пошаговые инструкции по поиску в журнале аудита Office 365 можно узнать в статье [Поиск в журнале аудита в центре безопасности & соответствия требованиям](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="8b6ab-121">For step-by-step instructions on searching the Office 365 audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
    
## <a name="turn-on-audit-log-search"></a><span data-ttu-id="8b6ab-122">Включение поиска в журнале аудита</span><span class="sxs-lookup"><span data-stu-id="8b6ab-122">Turn on audit log search</span></span>

<span data-ttu-id="8b6ab-123">Для включения поиска журнала аудита в Office 365 можно воспользоваться центром безопасности & соответствия требованиям или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8b6ab-123">You can use the Security & Compliance Center or PowerShell to turn on audit log search in Office 365.</span></span> <span data-ttu-id="8b6ab-124">После включения поиска в журнале аудита может потребоваться несколько часов, прежде чем вы сможете вернуть результаты при поиске в журнале аудита.</span><span class="sxs-lookup"><span data-stu-id="8b6ab-124">It may take several hours after you turn on audit log search before you can return results when you search the audit log.</span></span> <span data-ttu-id="8b6ab-125">Чтобы включить поиск журнала аудита, необходимо назначить роль журналов аудита в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8b6ab-125">You have to be assigned the Audit Logs role in Exchange Online to turn on audit log search.</span></span>
  
### <a name="use-the-security--compliance-center-to-turn-on-audit-log-search"></a><span data-ttu-id="8b6ab-126">Использование центра безопасности & соответствия требованиям для включения поиска в журнале аудита</span><span class="sxs-lookup"><span data-stu-id="8b6ab-126">Use the Security & Compliance Center to turn on audit log search</span></span>

1. <span data-ttu-id="8b6ab-127">В центре безопасности & соответствия требованиям выберите Поиск в \*\*\*\* \> **журнале аудита**поиска.</span><span class="sxs-lookup"><span data-stu-id="8b6ab-127">In the Security & Compliance Center, go to **Search** \> **Audit log search**.</span></span>
    
   <span data-ttu-id="8b6ab-128">Отображается баннер, в котором нужно включить аудит для записи действий пользователей и администраторов.</span><span class="sxs-lookup"><span data-stu-id="8b6ab-128">A banner is displayed saying that auditing has to be turned on to record user and admin activity.</span></span>

2. <span data-ttu-id="8b6ab-129">Щелкните **включить аудит**.</span><span class="sxs-lookup"><span data-stu-id="8b6ab-129">Click **Turn on auditing**.</span></span>
    
    ![Щелкните Включить аудит](media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    <span data-ttu-id="8b6ab-131">Баннер обновляется, чтобы сказать, что журнал аудита подготавливается, и вы можете выполнять поиск действий пользователей и администраторов через несколько часов.</span><span class="sxs-lookup"><span data-stu-id="8b6ab-131">The banner is updated to say the audit log is being prepared and that you can search for user and admin activity in a few hours.</span></span>
    
### <a name="use-powershell-to-turn-on-audit-log-search"></a><span data-ttu-id="8b6ab-132">Включение поиска в журнале аудита с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="8b6ab-132">Use PowerShell to turn on audit log search</span></span>

1. [<span data-ttu-id="8b6ab-133">Подключение к PowerShell Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8b6ab-133">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. <span data-ttu-id="8b6ab-134">Выполните следующую команду PowerShell, чтобы включить поиск журнала аудита в Office 365.</span><span class="sxs-lookup"><span data-stu-id="8b6ab-134">Run the following PowerShell command to turn on audit log search in Office 365.</span></span>
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="8b6ab-135">Отображается сообщение о том, что изменение вступит в силу до 60 минут.</span><span class="sxs-lookup"><span data-stu-id="8b6ab-135">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-audit-log-search"></a><span data-ttu-id="8b6ab-136">Отключение поиска в журнале аудита</span><span class="sxs-lookup"><span data-stu-id="8b6ab-136">Turn off audit log search</span></span>

<span data-ttu-id="8b6ab-137">Чтобы отключить поиск в журнале аудита, необходимо использовать удаленную оболочку PowerShell, подключенную к организации Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8b6ab-137">You have to use remote PowerShell connected to your Exchange Online organization to turn off audit log search.</span></span> <span data-ttu-id="8b6ab-138">Аналогично включению поиска в журнале аудита необходимо назначить роль журналов аудита в Exchange Online, чтобы отключить поиск в журнале аудита.</span><span class="sxs-lookup"><span data-stu-id="8b6ab-138">Similar to turning on audit log search, you have to be assigned the Audit Logs role in Exchange Online to turn off audit log search.</span></span>
  
1. [<span data-ttu-id="8b6ab-139">Подключение к PowerShell Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8b6ab-139">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. <span data-ttu-id="8b6ab-140">Выполните следующую команду PowerShell, чтобы отключить поиск в журнале аудита в Office 365.</span><span class="sxs-lookup"><span data-stu-id="8b6ab-140">Run the following PowerShell command to turn off audit log search in Office 365.</span></span>
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="8b6ab-141">Через некоторое время убедитесь, что поиск в журнале аудита отключен (отключен).</span><span class="sxs-lookup"><span data-stu-id="8b6ab-141">After a while, verify that audit log search is turned off (disabled).</span></span> <span data-ttu-id="8b6ab-142">Это можно сделать двумя способами:</span><span class="sxs-lookup"><span data-stu-id="8b6ab-142">There are two ways to do this:</span></span>
    
    - <span data-ttu-id="8b6ab-143">В PowerShell выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8b6ab-143">In PowerShell, run the following command:</span></span>

            ```
            Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
            ```

           The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned off. 
    
    - <span data-ttu-id="8b6ab-144">В центре безопасности & соответствия требованиям выберите Поиск в \*\*\*\* \> **журнале аудита**поиска.</span><span class="sxs-lookup"><span data-stu-id="8b6ab-144">In the Security & Compliance Center, go to **Search** \> **Audit log search**.</span></span>
    
           A banner is displayed saying that auditing has to be turned on in order to record user and admin activity.
