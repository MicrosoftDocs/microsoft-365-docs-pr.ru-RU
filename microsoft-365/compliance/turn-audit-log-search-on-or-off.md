---
title: Включение и отключение поиска в журнале аудита
f1.keywords:
- NOCSH
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
description: Вы можете включить функцию поиска журнала аудита в центре безопасности & соответствия требованиям. Если вы передумали, вы можете включить его в любое время. Если поиск в журнале аудита отключен, администраторы не могут выполнять поиск действий пользователей и администраторов в журнале аудита Microsoft 365 в Организации.
ms.openlocfilehash: f3d88f62f466d9c868dfc6addb5865e144f5223b
ms.sourcegitcommit: 56772bed89516cebc5eb370e292ccfbb4889cb38
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "44330793"
---
# <a name="turn-audit-log-search-on-or-off"></a><span data-ttu-id="b31c7-105">Включение и отключение поиска в журнале аудита</span><span class="sxs-lookup"><span data-stu-id="b31c7-105">Turn audit log search on or off</span></span>

<span data-ttu-id="b31c7-106">Перед началом поиска в журнале аудита необходимо включить ведение журнала аудита (или другого администратора).</span><span class="sxs-lookup"><span data-stu-id="b31c7-106">You (or another admin) must turn on audit logging before you can start searching the audit log.</span></span> <span data-ttu-id="b31c7-107">Когда включен Поиск в журнале аудита в центре безопасности & соответствия требованиям, действия пользователей и администраторов из вашей организации записываются в журнал аудита и хранятся в течение 90 дней, а также в соответствии с лицензией, назначенной пользователям.</span><span class="sxs-lookup"><span data-stu-id="b31c7-107">When audit log search in the Security & Compliance Center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days, and up to one year depending on the license assigned to users.</span></span> <span data-ttu-id="b31c7-108">Тем не менее, в организации могут возникнуть причины, по которым не нужно заносить и хранить данные журнала аудита.</span><span class="sxs-lookup"><span data-stu-id="b31c7-108">However, your organization may have reasons for not wanting to record and retain audit log data.</span></span> <span data-ttu-id="b31c7-109">В таких случаях глобальный администратор может отключить аудит в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b31c7-109">In those cases, a global admin may decide to turn off auditing in Microsoft 365.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b31c7-110">Если отключить поиск в журнале аудита в Microsoft 365, вы не сможете использовать API действий управления Office 365 или метку Azure для доступа к данным аудита в Организации.</span><span class="sxs-lookup"><span data-stu-id="b31c7-110">If you turn off audit log search in Microsoft 365, you can't use the Office 365 Management Activity API or Azure Sentinel to access auditing data for your organization.</span></span> <span data-ttu-id="b31c7-111">Чтобы отключить поиск в журнале аудита, выполнив действия, описанные в этой статье, это означает, что при поиске в журнале аудита с помощью центра безопасности & соответствия требованиям или при запуске командлета **Search-UnifiedAuditLog** в Exchange Online PowerShell не будет возвращено никаких результатов.</span><span class="sxs-lookup"><span data-stu-id="b31c7-111">Turning off audit log search by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="b31c7-112">Это также означает, что журналы аудита не будут доступны через API действий управления Office 365 или Sentinel.</span><span class="sxs-lookup"><span data-stu-id="b31c7-112">This also means that audit logs won't be available through the Office 365 Management Activity API or Azure Sentinel.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="b31c7-113">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="b31c7-113">Before you begin</span></span>

- <span data-ttu-id="b31c7-114">Роль журналов аудита в Exchange Online должна быть назначена для включения или отключения поиска журнала аудита в организации Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b31c7-114">You have to be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Microsoft 365 organization.</span></span> <span data-ttu-id="b31c7-115">По умолчанию эта роль назначается группам ролей "Управление соответствием требованиям" и "Управление организацией" на странице " **разрешения** " в центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="b31c7-115">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="b31c7-116">Глобальные администраторы в Microsoft 365 являются участниками группы ролей Управление организацией в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b31c7-116">Global admins in Microsoft 365 are members of the Organization Management role group in Exchange Online.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="b31c7-117">Пользователям необходимо назначить разрешения в Exchange Online, чтобы включить или отключить поиск в журнале аудита.</span><span class="sxs-lookup"><span data-stu-id="b31c7-117">Users have to be assigned permissions in Exchange Online to turn audit log search on or off.</span></span> <span data-ttu-id="b31c7-118">Если вы назначили пользователям роль "журналы аудита" на странице " **разрешения** " центра безопасности & соответствия требованиям, они не смогут включать или отключать поиск в журнале аудита.</span><span class="sxs-lookup"><span data-stu-id="b31c7-118">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn audit log search on or off.</span></span> <span data-ttu-id="b31c7-119">Это вызвано тем, что базовый командлет является командлетом Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b31c7-119">This is because the underlying cmdlet is an Exchange Online cmdlet.</span></span> 
    
- <span data-ttu-id="b31c7-120">Пошаговые инструкции по поиску в журнале аудита приведены [в статье Поиск в журнале аудита в центре безопасности & соответствия требованиям](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="b31c7-120">For step-by-step instructions on searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> <span data-ttu-id="b31c7-121">Дополнительные сведения об API действий по управлению Microsoft 365 приведены в разделе [Начало работы с API управления microsoft 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span><span class="sxs-lookup"><span data-stu-id="b31c7-121">For more information about the Microsoft 365 Management Activity API, see [Get started with Microsoft 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>
    
## <a name="turn-on-audit-log-search"></a><span data-ttu-id="b31c7-122">Включение поиска в журнале аудита</span><span class="sxs-lookup"><span data-stu-id="b31c7-122">Turn on audit log search</span></span>

<span data-ttu-id="b31c7-123">Для включения поиска журнала аудита в Microsoft 365 можно использовать центр безопасности & соответствия требованиям или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b31c7-123">You can use the Security & Compliance Center or PowerShell to turn on audit log search in Microsoft 365.</span></span> <span data-ttu-id="b31c7-124">После включения поиска в журнале аудита может потребоваться несколько часов, прежде чем вы сможете вернуть результаты при поиске в журнале аудита.</span><span class="sxs-lookup"><span data-stu-id="b31c7-124">It may take several hours after you turn on audit log search before you can return results when you search the audit log.</span></span> <span data-ttu-id="b31c7-125">Чтобы включить поиск журнала аудита, необходимо назначить роль журналов аудита в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b31c7-125">You have to be assigned the Audit Logs role in Exchange Online to turn on audit log search.</span></span>
  
### <a name="use-the-security--compliance-center-to-turn-on-audit-log-search"></a><span data-ttu-id="b31c7-126">Использование центра безопасности & соответствия требованиям для включения поиска в журнале аудита</span><span class="sxs-lookup"><span data-stu-id="b31c7-126">Use the Security & Compliance Center to turn on audit log search</span></span>

1. <span data-ttu-id="b31c7-127">[Перейдите в центр безопасности & соответствия требованиям](https://protection.office.com) и войдите в систему.</span><span class="sxs-lookup"><span data-stu-id="b31c7-127">[Go to the Security & Compliance Center](https://protection.office.com) and sign in.</span></span>

2. <span data-ttu-id="b31c7-128">В центре безопасности & соответствия требованиям выберите Поиск в **Search** \> **журнале аудита**поиска.</span><span class="sxs-lookup"><span data-stu-id="b31c7-128">In the Security & Compliance Center, go to **Search** \> **Audit log search**.</span></span>

   <span data-ttu-id="b31c7-129">Отображается баннер, в котором нужно включить аудит для записи действий пользователей и администраторов.</span><span class="sxs-lookup"><span data-stu-id="b31c7-129">A banner is displayed saying that auditing has to be turned on to record user and admin activity.</span></span>

3. <span data-ttu-id="b31c7-130">Щелкните **включить аудит**.</span><span class="sxs-lookup"><span data-stu-id="b31c7-130">Click **Turn on auditing**.</span></span>

    ![Щелкните Включить аудит](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    <span data-ttu-id="b31c7-132">Баннер обновляется, чтобы сказать, что журнал аудита подготавливается, и вы можете выполнять поиск действий пользователей и администраторов через несколько часов.</span><span class="sxs-lookup"><span data-stu-id="b31c7-132">The banner is updated to say the audit log is being prepared and that you can search for user and admin activity in a few hours.</span></span>

### <a name="use-powershell-to-turn-on-audit-log-search"></a><span data-ttu-id="b31c7-133">Включение поиска в журнале аудита с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="b31c7-133">Use PowerShell to turn on audit log search</span></span>

1. [<span data-ttu-id="b31c7-134">Подключение к PowerShell Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b31c7-134">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. <span data-ttu-id="b31c7-135">Выполните следующую команду PowerShell, чтобы включить поиск журнала аудита в Office 365.</span><span class="sxs-lookup"><span data-stu-id="b31c7-135">Run the following PowerShell command to turn on audit log search in Office 365.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="b31c7-136">Отображается сообщение о том, что изменение вступит в силу до 60 минут.</span><span class="sxs-lookup"><span data-stu-id="b31c7-136">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-audit-log-search"></a><span data-ttu-id="b31c7-137">Отключение поиска в журнале аудита</span><span class="sxs-lookup"><span data-stu-id="b31c7-137">Turn off audit log search</span></span>

<span data-ttu-id="b31c7-138">Чтобы отключить поиск в журнале аудита, необходимо использовать удаленную оболочку PowerShell, подключенную к организации Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b31c7-138">You have to use remote PowerShell connected to your Exchange Online organization to turn off audit log search.</span></span> <span data-ttu-id="b31c7-139">Аналогично включению поиска в журнале аудита необходимо назначить роль журналов аудита в Exchange Online, чтобы отключить поиск в журнале аудита.</span><span class="sxs-lookup"><span data-stu-id="b31c7-139">Similar to turning on audit log search, you have to be assigned the Audit Logs role in Exchange Online to turn off audit log search.</span></span>
  
1. [<span data-ttu-id="b31c7-140">Подключение к PowerShell Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b31c7-140">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. <span data-ttu-id="b31c7-141">Выполните следующую команду PowerShell, чтобы отключить поиск в журнале аудита в Office 365.</span><span class="sxs-lookup"><span data-stu-id="b31c7-141">Run the following PowerShell command to turn off audit log search in Office 365.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="b31c7-142">Через некоторое время убедитесь, что поиск в журнале аудита отключен (отключен).</span><span class="sxs-lookup"><span data-stu-id="b31c7-142">After a while, verify that audit log search is turned off (disabled).</span></span> <span data-ttu-id="b31c7-143">Это можно сделать двумя способами:</span><span class="sxs-lookup"><span data-stu-id="b31c7-143">There are two ways to do this:</span></span>

    - <span data-ttu-id="b31c7-144">В PowerShell выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b31c7-144">In PowerShell, run the following command:</span></span>

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

      <span data-ttu-id="b31c7-145">Значение `False` свойства _унифиедаудитлогинжестионенаблед_ указывает на то, что поиск журнала аудита отключен.</span><span class="sxs-lookup"><span data-stu-id="b31c7-145">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned off.</span></span> 

    - <span data-ttu-id="b31c7-146">В [центре безопасности & соответствия требованиям](https://protection.office.com)выберите Поиск в **Search** \> **журнале аудита**поиска.</span><span class="sxs-lookup"><span data-stu-id="b31c7-146">In the [Security & Compliance Center](https://protection.office.com), go to **Search** \> **Audit log search**.</span></span>

      <span data-ttu-id="b31c7-147">Отображается баннер, в котором необходимо включить аудит для записи действий пользователей и администраторов.</span><span class="sxs-lookup"><span data-stu-id="b31c7-147">A banner is displayed saying that auditing has to be turned on in order to record user and admin activity.</span></span>