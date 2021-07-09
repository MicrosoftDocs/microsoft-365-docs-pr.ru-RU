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
ms.openlocfilehash: dd39b883036ce6060aef71c6a927c03f391d827f
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341500"
---
# <a name="turn-auditing-on-or-off"></a><span data-ttu-id="f9887-103">Включение и отключение аудита</span><span class="sxs-lookup"><span data-stu-id="f9887-103">Turn auditing on or off</span></span>

<span data-ttu-id="f9887-104">По умолчанию ведение журналов аудита включено для организаций, использующих Microsoft 365 и Office 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="f9887-104">Audit logging is turned on by default for Microsoft 365 and Office 365 enterprise organizations.</span></span> <span data-ttu-id="f9887-105">При включенном Центр соответствия требованиям Microsoft 365 аудите действия пользователя и администратора вашей организации записывают в журнал аудита и сохраняются в течение 90 дней и до одного года в зависимости от лицензии, назначенной пользователям.</span><span class="sxs-lookup"><span data-stu-id="f9887-105">When auditing in the Microsoft 365 compliance center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days, and up to one year depending on the license assigned to users.</span></span> <span data-ttu-id="f9887-106">Однако у вашей организации могут быть причины, по которой вы не хотите записывать и хранить данные журнала аудита.</span><span class="sxs-lookup"><span data-stu-id="f9887-106">However, your organization may have reasons for not wanting to record and retain audit log data.</span></span> <span data-ttu-id="f9887-107">В этих случаях глобальный администратор может принять решение отключить аудит в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f9887-107">In those cases, a global admin may decide to turn off auditing in Microsoft 365.</span></span>

<span data-ttu-id="f9887-108">При настройке Microsoft 365 или Office 365 организации можно проверить состояние аудита для организации.</span><span class="sxs-lookup"><span data-stu-id="f9887-108">When setting up a new Microsoft 365 or Office 365 organization, you can verify the auditing status for your organization.</span></span> <span data-ttu-id="f9887-109">Инструкции см. в разделе Проверка состояния аудита для [вашей](#verify-the-auditing-status-for-your-organization) организации в этой статье.</span><span class="sxs-lookup"><span data-stu-id="f9887-109">For instructions, see the [Verify the auditing status for your organization](#verify-the-auditing-status-for-your-organization) section in this article.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f9887-110">Если вы отключите аудит в Microsoft 365, вы не можете использовать API Office 365 управления или Azure Sentinel для доступа к данным аудита для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="f9887-110">If you turn off auditing in Microsoft 365, you can't use the Office 365 Management Activity API or Azure Sentinel to access auditing data for your organization.</span></span> <span data-ttu-id="f9887-111">Отключение аудита, следуя шагам в этой статье, означает, что результаты не будут возвращены при поиске журнала аудита с помощью Центр соответствия требованиям Microsoft 365 или при запуске **cmdlet Search-UnifiedAuditLog** в Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f9887-111">Turning off auditing by following the steps in this article means that no results will be returned when you search the audit log using the Microsoft 365 compliance center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="f9887-112">Это также означает, что журналы аудита не будут доступны через API Office 365 управления или Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="f9887-112">This also means that audit logs won't be available through the Office 365 Management Activity API or Azure Sentinel.</span></span>
  
## <a name="before-you-turn-auditing-on-or-off"></a><span data-ttu-id="f9887-113">Прежде чем включить аудит или отключить</span><span class="sxs-lookup"><span data-stu-id="f9887-113">Before you turn auditing on or off</span></span>

- <span data-ttu-id="f9887-114">Для того чтобы включить или отключить аудит в Exchange Online организации, необходимо Exchange Online роли Microsoft 365 журналов аудита.</span><span class="sxs-lookup"><span data-stu-id="f9887-114">You have to be assigned the Audit Logs role in Exchange Online to turn auditing on or off in your Microsoft 365 organization.</span></span> <span data-ttu-id="f9887-115">По умолчанию эта роль назначена группам ролей управления соответствием требованиям и организации на странице **Permissions** в центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="f9887-115">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="f9887-116">Глобальные администраторы в Microsoft 365 являются членами группы ролей управления организацией в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f9887-116">Global admins in Microsoft 365 are members of the Organization Management role group in Exchange Online.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f9887-117">Пользователям должны быть назначены разрешения в Exchange Online, чтобы включить или отключить аудит.</span><span class="sxs-lookup"><span data-stu-id="f9887-117">Users have to be assigned permissions in Exchange Online to turn auditing on or off.</span></span> <span data-ttu-id="f9887-118">Если назначить пользователям роль журналов  аудита на странице Разрешения в Центр соответствия требованиям Microsoft 365, они не смогут включить или отключить аудит.</span><span class="sxs-lookup"><span data-stu-id="f9887-118">If you assign users the Audit Logs role on the **Permissions** page in the Microsoft 365 compliance center, they won't be able to turn auditing on or off.</span></span> <span data-ttu-id="f9887-119">Это потому, что в основном cmdlet является Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f9887-119">This is because the underlying cmdlet is an Exchange Online PowerShell cmdlet.</span></span>

- <span data-ttu-id="f9887-120">Пошаговая инструкция по поиску журнала аудита см. в [журнале Поиска аудита.](search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="f9887-120">For step-by-step instructions on searching the audit log, see [Search the audit log](search-the-audit-log-in-security-and-compliance.md).</span></span> <span data-ttu-id="f9887-121">Дополнительные сведения об API Microsoft 365 управления см. в Microsoft 365 [API](/office/office-365-management-api/get-started-with-office-365-management-apis)управления.</span><span class="sxs-lookup"><span data-stu-id="f9887-121">For more information about the Microsoft 365 Management Activity API, see [Get started with Microsoft 365 Management APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

## <a name="verify-the-auditing-status-for-your-organization"></a><span data-ttu-id="f9887-122">Проверка состояния аудита для организации</span><span class="sxs-lookup"><span data-stu-id="f9887-122">Verify the auditing status for your organization</span></span>

<span data-ttu-id="f9887-123">Чтобы убедиться, что аудит включен для организации, можно выполнить следующую команду в [Exchange Online PowerShell:](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="f9887-123">To verify that auditing is turned on for your organization, you can run the following command in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

```powershell
Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
```

<span data-ttu-id="f9887-124">Значение свойства `True`  _UnifiedAuditLogIngestionEnabled_ указывает, что аудит включен.</span><span class="sxs-lookup"><span data-stu-id="f9887-124">A value of `True` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that auditing is turned on.</span></span> <span data-ttu-id="f9887-125">Значение `False` указывает, что аудит не включен.</span><span class="sxs-lookup"><span data-stu-id="f9887-125">A value of `False` indicates that auditing is not turned on.</span></span>

## <a name="turn-on-auditing"></a><span data-ttu-id="f9887-126">Включи аудит</span><span class="sxs-lookup"><span data-stu-id="f9887-126">Turn on auditing</span></span>

<span data-ttu-id="f9887-127">Если аудит не включен для организации, его можно включить в Центр соответствия требованиям Microsoft 365 или с помощью Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f9887-127">If auditing is not turned on for your organization, you can turn it on in the Microsoft 365 compliance center or by using Exchange Online PowerShell.</span></span> <span data-ttu-id="f9887-128">Может потребоваться несколько часов после того, как вы включит аудит, прежде чем вы сможете возвращать результаты при поиске журнала аудита.</span><span class="sxs-lookup"><span data-stu-id="f9887-128">It may take several hours after you turn on auditing before you can return results when you search the audit log.</span></span>
  
### <a name="use-the-compliance-center-to-turn-on-auditing"></a><span data-ttu-id="f9887-129">Используйте центр соответствия требованиям, чтобы включить аудит</span><span class="sxs-lookup"><span data-stu-id="f9887-129">Use the compliance center to turn on auditing</span></span>

1. <span data-ttu-id="f9887-130">Перейдите на <https://compliance.microsoft.com> и войдите.</span><span class="sxs-lookup"><span data-stu-id="f9887-130">Go to <https://compliance.microsoft.com> and sign in.</span></span>

2. <span data-ttu-id="f9887-131">В левой области навигации Центр соответствия требованиям Microsoft 365 нажмите **кнопку Аудит**.</span><span class="sxs-lookup"><span data-stu-id="f9887-131">In the left navigation pane of the Microsoft 365 compliance center, click **Audit**.</span></span>

   <span data-ttu-id="f9887-132">Если аудит не включен для вашей организации, отображается баннер, в результате чего начинается запись действий пользователя и администратора.</span><span class="sxs-lookup"><span data-stu-id="f9887-132">If auditing is not turned on for your organization, a banner is displayed prompting you start recording user and admin activity.</span></span>

   ![Баннер на странице Аудит](../media/AuditingBanner.png)

3. <span data-ttu-id="f9887-134">Нажмите **кнопку Начните запись пользователя и баннера действий администратора.**</span><span class="sxs-lookup"><span data-stu-id="f9887-134">Click the **Start recording user and admin activity** banner.</span></span>

   <span data-ttu-id="f9887-135">На то, чтобы изменение вступает в силу, может потребоваться до 60 минут.</span><span class="sxs-lookup"><span data-stu-id="f9887-135">It may take up to 60 minutes for the change to take effect.</span></span>

### <a name="use-powershell-to-turn-on-auditing"></a><span data-ttu-id="f9887-136">Чтобы включить аудит, используйте PowerShell</span><span class="sxs-lookup"><span data-stu-id="f9887-136">Use PowerShell to turn on auditing</span></span>

1. <span data-ttu-id="f9887-137">[Подключение к PowerShell для Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f9887-137">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="f9887-138">Запустите следующую команду PowerShell, чтобы включить аудит.</span><span class="sxs-lookup"><span data-stu-id="f9887-138">Run the following PowerShell command to turn on auditing.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="f9887-139">Отображается сообщение о том, что для в действие изменения может потребоваться до 60 минут.</span><span class="sxs-lookup"><span data-stu-id="f9887-139">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-auditing"></a><span data-ttu-id="f9887-140">Отключение аудита</span><span class="sxs-lookup"><span data-stu-id="f9887-140">Turn off auditing</span></span>

<span data-ttu-id="f9887-141">Чтобы отключить аудит Exchange Online PowerShell, необходимо использовать Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f9887-141">You have to use Exchange Online PowerShell to turn off auditing.</span></span>
  
1. <span data-ttu-id="f9887-142">[Подключение к PowerShell для Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f9887-142">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="f9887-143">Запустите следующую команду PowerShell, чтобы отключить аудит.</span><span class="sxs-lookup"><span data-stu-id="f9887-143">Run the following PowerShell command to turn off auditing.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="f9887-144">Через некоторое время убедитесь, что аудит отключен (отключен).</span><span class="sxs-lookup"><span data-stu-id="f9887-144">After a while, verify that auditing is turned off (disabled).</span></span> <span data-ttu-id="f9887-145">Это можно сделать двумя способами:</span><span class="sxs-lookup"><span data-stu-id="f9887-145">There are two ways to do this:</span></span>

    - <span data-ttu-id="f9887-146">В Exchange Online PowerShell запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f9887-146">In Exchange Online PowerShell, run the following command:</span></span>

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      <span data-ttu-id="f9887-147">Значение свойства  `False`  _UnifiedAuditLogIngestionEnabled_ указывает на отключение аудита.</span><span class="sxs-lookup"><span data-stu-id="f9887-147">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that auditing is turned off.</span></span>

    - <span data-ttu-id="f9887-148">Перейдите на **страницу Аудит** в Центр соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f9887-148">Go to the **Audit** page in the Microsoft 365 compliance center.</span></span>

      <span data-ttu-id="f9887-149">Если аудит не включен для вашей организации, отображается баннер, в результате чего начинается запись действий пользователя и администратора.</span><span class="sxs-lookup"><span data-stu-id="f9887-149">If auditing is not turned on for your organization, a banner is displayed prompting you start recording user and admin activity.</span></span>
