---
title: Включение и отключение аудита
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
description: Как включить или отключить функцию поиска журнала аудита в Центр соответствия требованиям Microsoft 365, чтобы включить или отключить возможность администраторов для поиска журнала аудита.
ms.openlocfilehash: 7c55443eda9a99ff4ef153d8564fd9ac43fcc549
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105312"
---
# <a name="turn-auditing-on-or-off"></a><span data-ttu-id="08e50-103">Включение и отключение аудита</span><span class="sxs-lookup"><span data-stu-id="08e50-103">Turn auditing on or off</span></span>

<span data-ttu-id="08e50-104">По умолчанию ведение журналов аудита включено для организаций, использующих Microsoft 365 и Office 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="08e50-104">Audit logging is turned on by default for Microsoft 365 and Office 365 enterprise organizations.</span></span> <span data-ttu-id="08e50-105">Сюда также входят организации с подпиской E3/G3 или E5/G5.</span><span class="sxs-lookup"><span data-stu-id="08e50-105">This includes organizations with E3/G3 or E5/G5 subscriptions.</span></span> <span data-ttu-id="08e50-106">При включенном аудите в центре соответствия требованиям действия пользователя и администратора организации записывают в журнал аудита и сохраняются в течение 90 дней и до одного года в зависимости от лицензии, назначенной пользователям.</span><span class="sxs-lookup"><span data-stu-id="08e50-106">When auditing in the compliance center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days, and up to one year depending on the license assigned to users.</span></span> <span data-ttu-id="08e50-107">Однако у вашей организации могут быть причины, по которой вы не хотите записывать и хранить данные журнала аудита.</span><span class="sxs-lookup"><span data-stu-id="08e50-107">However, your organization may have reasons for not wanting to record and retain audit log data.</span></span> <span data-ttu-id="08e50-108">В этих случаях глобальный администратор может принять решение отключить аудит в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="08e50-108">In those cases, a global admin may decide to turn off auditing in Microsoft 365.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="08e50-109">Если вы отключите аудит в Microsoft 365, вы не можете использовать API Office 365 управления или Azure Sentinel для доступа к данным аудита для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="08e50-109">If you turn off auditing in Microsoft 365, you can't use the Office 365 Management Activity API or Azure Sentinel to access auditing data for your organization.</span></span> <span data-ttu-id="08e50-110">Отключение аудита, следуя шагам в этой статье, означает, что результаты не будут возвращены при поиске журнала аудита с помощью Центра соответствия требованиям безопасности & или при запуске **cmdlet Search-UnifiedAuditLog** в Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="08e50-110">Turning off auditing by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="08e50-111">Это также означает, что журналы аудита не будут доступны через API Office 365 управления или Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="08e50-111">This also means that audit logs won't be available through the Office 365 Management Activity API or Azure Sentinel.</span></span>
  
## <a name="before-you-turn-auditing-on-or-off"></a><span data-ttu-id="08e50-112">Прежде чем включить аудит или отключить</span><span class="sxs-lookup"><span data-stu-id="08e50-112">Before you turn auditing on or off</span></span>

- <span data-ttu-id="08e50-113">Для того чтобы включить или отключить аудит в Exchange Online организации, необходимо Exchange Online роли Microsoft 365 журналов аудита.</span><span class="sxs-lookup"><span data-stu-id="08e50-113">You have to be assigned the Audit Logs role in Exchange Online to turn auditing on or off in your Microsoft 365 organization.</span></span> <span data-ttu-id="08e50-114">По умолчанию эта роль назначена группам ролей управления соответствием требованиям и организации на странице **Permissions** в центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="08e50-114">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="08e50-115">Глобальные администраторы в Microsoft 365 являются членами группы ролей управления организацией в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="08e50-115">Global admins in Microsoft 365 are members of the Organization Management role group in Exchange Online.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="08e50-116">Пользователям должны быть назначены разрешения в Exchange Online, чтобы включить или отключить аудит.</span><span class="sxs-lookup"><span data-stu-id="08e50-116">Users have to be assigned permissions in Exchange Online to turn auditing on or off.</span></span> <span data-ttu-id="08e50-117">Если назначить пользователям роль журналов аудита на странице **Разрешения** в Центре соответствия требованиям & безопасности, они не смогут включить или отключить аудит.</span><span class="sxs-lookup"><span data-stu-id="08e50-117">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn auditing on or off.</span></span> <span data-ttu-id="08e50-118">Это потому, что в основном cmdlet является Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="08e50-118">This is because the underlying cmdlet is an Exchange Online PowerShell cmdlet.</span></span>

- <span data-ttu-id="08e50-119">Пошаговая инструкция по поиску журнала аудита см. в журнале Search [the audit log in the Security & Compliance Center.](search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="08e50-119">For step-by-step instructions on searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> <span data-ttu-id="08e50-120">Дополнительные сведения об API Microsoft 365 управления см. в Microsoft 365 [API](/office/office-365-management-api/get-started-with-office-365-management-apis)управления.</span><span class="sxs-lookup"><span data-stu-id="08e50-120">For more information about the Microsoft 365 Management Activity API, see [Get started with Microsoft 365 Management APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

- <span data-ttu-id="08e50-121">Чтобы убедиться, что аудит включен, можно выполнить следующую команду в Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="08e50-121">To verify that auditing is turned on, you can run the following command in Exchange Online PowerShell:</span></span>

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

    <span data-ttu-id="08e50-122">Значение свойства  `True`  _UnifiedAuditLogIngestionEnabled_ указывает, что аудит включен.</span><span class="sxs-lookup"><span data-stu-id="08e50-122">The value of  `True` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that auditing is turned on.</span></span> 

## <a name="turn-on-auditing"></a><span data-ttu-id="08e50-123">Включи аудит</span><span class="sxs-lookup"><span data-stu-id="08e50-123">Turn on auditing</span></span>

<span data-ttu-id="08e50-124">Если аудит не включен для организации, его можно включить в центре соответствия требованиям или с помощью Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="08e50-124">If auditing is not turned on for your organization, you can turn it on in the compliance center or by using Exchange Online PowerShell.</span></span> <span data-ttu-id="08e50-125">Может потребоваться несколько часов после того, как вы включит аудит, прежде чем вы сможете возвращать результаты при поиске журнала аудита.</span><span class="sxs-lookup"><span data-stu-id="08e50-125">It may take several hours after you turn on auditing before you can return results when you search the audit log.</span></span>
  
### <a name="use-the-compliance-center-to-turn-on-auditing"></a><span data-ttu-id="08e50-126">Используйте центр соответствия требованиям, чтобы включить аудит</span><span class="sxs-lookup"><span data-stu-id="08e50-126">Use the compliance center to turn on auditing</span></span>

1. <span data-ttu-id="08e50-127">Перейдите на <https://compliance.microsoft.com> и войдите.</span><span class="sxs-lookup"><span data-stu-id="08e50-127">Go to <https://compliance.microsoft.com> and sign in.</span></span>

2. <span data-ttu-id="08e50-128">В левой области навигации Центр соответствия требованиям Microsoft 365 нажмите кнопку **Показать** все, а затем нажмите **аудит**.</span><span class="sxs-lookup"><span data-stu-id="08e50-128">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **Audit**.</span></span>

   <span data-ttu-id="08e50-129">Если аудит не включен для вашей организации, отображается баннер, в результате чего начинается запись действий пользователя и администратора.</span><span class="sxs-lookup"><span data-stu-id="08e50-129">If auditing is not turned on for your organization, a banner is displayed prompting you start recording user and admin activity.</span></span>

   ![Баннер на странице Аудит](../media/AuditingBanner.png)

3. <span data-ttu-id="08e50-131">Нажмите **кнопку Начните запись пользователя и баннера действий администратора.**</span><span class="sxs-lookup"><span data-stu-id="08e50-131">Click the **Start recording user and admin activity** banner.</span></span>

   <span data-ttu-id="08e50-132">На то, чтобы изменение вступает в силу, может потребоваться до 60 минут.</span><span class="sxs-lookup"><span data-stu-id="08e50-132">It may take up to 60 minutes for the change to take effect.</span></span>

### <a name="use-powershell-to-turn-on-auditing"></a><span data-ttu-id="08e50-133">Чтобы включить аудит, используйте PowerShell</span><span class="sxs-lookup"><span data-stu-id="08e50-133">Use PowerShell to turn on auditing</span></span>

1. [<span data-ttu-id="08e50-134">Подключение к PowerShell Exchange Online</span><span class="sxs-lookup"><span data-stu-id="08e50-134">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)

2. <span data-ttu-id="08e50-135">Запустите следующую команду PowerShell, чтобы включить аудит в Office 365.</span><span class="sxs-lookup"><span data-stu-id="08e50-135">Run the following PowerShell command to turn on auditing in Office 365.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="08e50-136">Отображается сообщение о том, что для в действие изменения может потребоваться до 60 минут.</span><span class="sxs-lookup"><span data-stu-id="08e50-136">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-auditing"></a><span data-ttu-id="08e50-137">Отключение аудита</span><span class="sxs-lookup"><span data-stu-id="08e50-137">Turn off auditing</span></span>

<span data-ttu-id="08e50-138">Чтобы отключить аудит Exchange Online PowerShell, необходимо использовать Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="08e50-138">You have to use Exchange Online PowerShell to turn off auditing.</span></span>
  
1. [<span data-ttu-id="08e50-139">Подключение к PowerShell Exchange Online</span><span class="sxs-lookup"><span data-stu-id="08e50-139">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)

2. <span data-ttu-id="08e50-140">Запустите следующую команду PowerShell, чтобы отключить аудит.</span><span class="sxs-lookup"><span data-stu-id="08e50-140">Run the following PowerShell command to turn off auditing.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="08e50-141">Через некоторое время убедитесь, что аудит отключен (отключен).</span><span class="sxs-lookup"><span data-stu-id="08e50-141">After a while, verify that auditing is turned off (disabled).</span></span> <span data-ttu-id="08e50-142">Это можно сделать двумя способами:</span><span class="sxs-lookup"><span data-stu-id="08e50-142">There are two ways to do this:</span></span>

    - <span data-ttu-id="08e50-143">В Exchange Online PowerShell запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="08e50-143">In Exchange Online PowerShell, run the following command:</span></span>

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      <span data-ttu-id="08e50-144">Значение свойства  `False`  _UnifiedAuditLogIngestionEnabled_ указывает на отключение аудита.</span><span class="sxs-lookup"><span data-stu-id="08e50-144">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that auditing is turned off.</span></span>

    - <span data-ttu-id="08e50-145">Перейдите на **страницу Аудит** в Центр соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="08e50-145">Go to the **Audit** page in the Microsoft 365 compliance center.</span></span>

      <span data-ttu-id="08e50-146">Если аудит не включен для вашей организации, отображается баннер, в результате чего начинается запись действий пользователя и администратора.</span><span class="sxs-lookup"><span data-stu-id="08e50-146">If auditing is not turned on for your organization, a banner is displayed prompting you start recording user and admin activity.</span></span>
