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
ms.custom: seo-marvel-apr2020
description: Как включить или отключить функцию поиска в журнале аудита в Центре безопасности & соответствия требованиям, чтобы включить или отключить возможность администраторов выполнять поиск в журнале аудита.
ms.openlocfilehash: 1f3da9671b9e5287d715a438a11b0a0eef164584
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976332"
---
# <a name="turn-audit-log-search-on-or-off"></a><span data-ttu-id="07fde-103">Включение и отключение поиска в журнале аудита</span><span class="sxs-lookup"><span data-stu-id="07fde-103">Turn audit log search on or off</span></span>

<span data-ttu-id="07fde-104">По умолчанию ведение журналов аудита включено для организаций, использующих Microsoft 365 и Office 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="07fde-104">Audit logging is turned on by default for Microsoft 365 and Office 365 enterprise organizations.</span></span> <span data-ttu-id="07fde-105">Сюда также входят организации с подпиской E3/G3 или E5/G5.</span><span class="sxs-lookup"><span data-stu-id="07fde-105">This includes organizations with E3/G3 or E5/G5 subscriptions.</span></span> <span data-ttu-id="07fde-106">Если поиск в журнале аудита в Центре соответствия требованиям включен, действия пользователей и администраторов из вашей организации записывают в журнал аудита и сохраняются в течение 90 дней и до одного года в зависимости от лицензии, назначенной пользователям.</span><span class="sxs-lookup"><span data-stu-id="07fde-106">When audit log search in the compliance center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days, and up to one year depending on the license assigned to users.</span></span> <span data-ttu-id="07fde-107">Однако у вашей организации могут быть причины не записывать и сохранять данные журнала аудита.</span><span class="sxs-lookup"><span data-stu-id="07fde-107">However, your organization may have reasons for not wanting to record and retain audit log data.</span></span> <span data-ttu-id="07fde-108">В таких случаях глобальный администратор может отключить аудит в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="07fde-108">In those cases, a global admin may decide to turn off auditing in Microsoft 365.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="07fde-109">Если вы отключите поиск в журнале аудита в Microsoft 365, вы не сможете использовать API действий управления Office 365 или Azure Sentinel для доступа к данным аудита для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="07fde-109">If you turn off audit log search in Microsoft 365, you can't use the Office 365 Management Activity API or Azure Sentinel to access auditing data for your organization.</span></span> <span data-ttu-id="07fde-110">Отключение поиска в журнале аудита с помощью действий в этой статье означает, что при поиске в журнале аудита с помощью Центра соответствия требованиям & безопасности или при выполнении в Exchange Online PowerShell в **Exchange** Online powerShell не будут возвращаться результаты.</span><span class="sxs-lookup"><span data-stu-id="07fde-110">Turning off audit log search by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="07fde-111">Это также означает, что журналы аудита будут недоступны через API действий управления Office 365 или Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="07fde-111">This also means that audit logs won't be available through the Office 365 Management Activity API or Azure Sentinel.</span></span>
  
## <a name="before-you-turn-audit-log-search-on-or-off"></a><span data-ttu-id="07fde-112">Перед тем как включить или отключить поиск в журнале аудита</span><span class="sxs-lookup"><span data-stu-id="07fde-112">Before you turn audit log search on or off</span></span>

- <span data-ttu-id="07fde-113">Вам должна быть назначена роль журналов аудита в Exchange Online, чтобы включить или отключить поиск в журнале аудита в организации Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="07fde-113">You have to be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Microsoft 365 organization.</span></span> <span data-ttu-id="07fde-114">По умолчанию эта роль назначена группам ролей "Управление соответствием требованиям" и "Управление организацией" на странице "Разрешения" в Центре администрирования Exchange. </span><span class="sxs-lookup"><span data-stu-id="07fde-114">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="07fde-115">Глобальные администраторы в Microsoft 365 являются членами группы ролей "Управление организацией" в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="07fde-115">Global admins in Microsoft 365 are members of the Organization Management role group in Exchange Online.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="07fde-116">Пользователям должны быть назначены разрешения в Exchange Online, чтобы включить или отключить поиск в журнале аудита.</span><span class="sxs-lookup"><span data-stu-id="07fde-116">Users have to be assigned permissions in Exchange Online to turn audit log search on or off.</span></span> <span data-ttu-id="07fde-117">Если назначить пользователям роль "Журналы аудита" на странице "Разрешения" в Центре безопасности & соответствия требованиям, они не смогут включить или отключить поиск в журнале аудита. </span><span class="sxs-lookup"><span data-stu-id="07fde-117">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn audit log search on or off.</span></span> <span data-ttu-id="07fde-118">Это потому, что в качестве его яви является exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="07fde-118">This is because the underlying cmdlet is an Exchange Online PowerShell cmdlet.</span></span> 
    
- <span data-ttu-id="07fde-119">Пошаговые инструкции по поиску в журнале аудита см. в журнале аудита в Центре безопасности [& соответствия требованиям.](search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="07fde-119">For step-by-step instructions on searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> <span data-ttu-id="07fde-120">Дополнительные сведения об API действий управления Microsoft 365 см. в руководстве "Начало работы с API управления [Microsoft 365".](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)</span><span class="sxs-lookup"><span data-stu-id="07fde-120">For more information about the Microsoft 365 Management Activity API, see [Get started with Microsoft 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

- <span data-ttu-id="07fde-121">Чтобы убедиться, что поиск в журнале аудита включен, можно выполнить следующую команду в Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="07fde-121">To verify that audit log search is turned on, you can run the following command in Exchange Online PowerShell:</span></span>

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

    <span data-ttu-id="07fde-122">Значение свойства  `True`  _UnifiedAuditLogIngestionEnabled_ указывает, что поиск в журнале аудита включен.</span><span class="sxs-lookup"><span data-stu-id="07fde-122">The value of  `True` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned on.</span></span> 
    
## <a name="turn-on-audit-log-search"></a><span data-ttu-id="07fde-123">Включить поиск в журнале аудита</span><span class="sxs-lookup"><span data-stu-id="07fde-123">Turn on audit log search</span></span>

<span data-ttu-id="07fde-124">Если поиск в журнале аудита не включен для вашей организации, его можно включить в Центре соответствия требованиям или с помощью Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="07fde-124">If audit log search is not turned on for your organization, you can turn it on in the compliance center or by using Exchange Online PowerShell.</span></span> <span data-ttu-id="07fde-125">После того как вы включите поиск в журнале аудита, может потребоваться несколько часов, прежде чем вы сможете возвращать результаты при поиске в журнале аудита.</span><span class="sxs-lookup"><span data-stu-id="07fde-125">It may take several hours after you turn on audit log search before you can return results when you search the audit log.</span></span>
  
### <a name="use-the-compliance-center-to-turn-on-audit-log-search"></a><span data-ttu-id="07fde-126">Включить поиск в журнале аудита с помощью Центра соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="07fde-126">Use the compliance center to turn on audit log search</span></span>

1. <span data-ttu-id="07fde-127">[Перейдите в Центр соответствия требованиям и](https://protection.office.com) войдите в нее.</span><span class="sxs-lookup"><span data-stu-id="07fde-127">[Go to the compliance center](https://protection.office.com) and sign in.</span></span>

2. <span data-ttu-id="07fde-128">В Центре соответствия требованиям перейдите к **поиску**  >  **в журнале аудита поиска.**</span><span class="sxs-lookup"><span data-stu-id="07fde-128">In the compliance center, go to **Search** > **Audit log search**.</span></span>

   <span data-ttu-id="07fde-129">Если поиск в журнале аудита не включен для вашей организации, отображается баннер о том, что аудит должен быть включен для записи действий пользователей и администраторов.</span><span class="sxs-lookup"><span data-stu-id="07fde-129">If audit log search is not turned on for your organization, a banner is displayed saying that auditing has to be turned on to record user and admin activity.</span></span>

3. <span data-ttu-id="07fde-130">Нажмите **кнопку "Включить аудит".**</span><span class="sxs-lookup"><span data-stu-id="07fde-130">Click **Turn on auditing**.</span></span>

    ![Нажмите кнопку "Включить аудит"](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    <span data-ttu-id="07fde-132">Этот баннер обновляется и сообщает о подготовке журнала аудита и о том, что вы можете искать действия пользователей и администраторов в течение нескольких часов.</span><span class="sxs-lookup"><span data-stu-id="07fde-132">The banner is updated to say the audit log is being prepared and that you can search for user and admin activity in a few hours.</span></span>

### <a name="use-powershell-to-turn-on-audit-log-search"></a><span data-ttu-id="07fde-133">Включить поиск в журнале аудита с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="07fde-133">Use PowerShell to turn on audit log search</span></span>

1. [<span data-ttu-id="07fde-134">Подключение к PowerShell Exchange Online</span><span class="sxs-lookup"><span data-stu-id="07fde-134">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. <span data-ttu-id="07fde-135">Чтобы включить поиск в журнале аудита в Office 365, запустите следующую команду PowerShell.</span><span class="sxs-lookup"><span data-stu-id="07fde-135">Run the following PowerShell command to turn on audit log search in Office 365.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="07fde-136">Отобразилось сообщение о том, что изменение вступает в силу в течение 60 минут.</span><span class="sxs-lookup"><span data-stu-id="07fde-136">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-audit-log-search"></a><span data-ttu-id="07fde-137">Отключение поиска в журнале аудита</span><span class="sxs-lookup"><span data-stu-id="07fde-137">Turn off audit log search</span></span>

<span data-ttu-id="07fde-138">Чтобы отключить поиск в журнале аудита, необходимо использовать Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="07fde-138">You have to use Exchange Online PowerShell to turn off audit log search.</span></span>
  
1. [<span data-ttu-id="07fde-139">Подключение к PowerShell Exchange Online</span><span class="sxs-lookup"><span data-stu-id="07fde-139">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. <span data-ttu-id="07fde-140">Чтобы отключить поиск в журнале аудита, запустите следующую команду PowerShell.</span><span class="sxs-lookup"><span data-stu-id="07fde-140">Run the following PowerShell command to turn off audit log search.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="07fde-141">Через некоторое время убедитесь, что поиск в журнале аудита отключен (отключен).</span><span class="sxs-lookup"><span data-stu-id="07fde-141">After a while, verify that audit log search is turned off (disabled).</span></span> <span data-ttu-id="07fde-142">Это можно сделать двумя способами:</span><span class="sxs-lookup"><span data-stu-id="07fde-142">There are two ways to do this:</span></span>

    - <span data-ttu-id="07fde-143">В Exchange Online PowerShell запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="07fde-143">In Exchange Online PowerShell, run the following command:</span></span>

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      <span data-ttu-id="07fde-144">Значение свойства  `False`  _UnifiedAuditLogIngestionEnabled_ указывает, что поиск в журнале аудита отключен.</span><span class="sxs-lookup"><span data-stu-id="07fde-144">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned off.</span></span> 

    - <span data-ttu-id="07fde-145">В Центре [соответствия требованиям перейдите](https://protection.office.com)к **поиску** \> **в журнале аудита поиска.**</span><span class="sxs-lookup"><span data-stu-id="07fde-145">In the [compliance center](https://protection.office.com), go to **Search** \> **Audit log search**.</span></span>

      <span data-ttu-id="07fde-146">Отобразилось баннер с надписью о том, что для записи действий пользователей и администраторов необходимо включен аудит.</span><span class="sxs-lookup"><span data-stu-id="07fde-146">A banner is displayed saying that auditing has to be turned on in order to record user and admin activity.</span></span>
