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
description: Как включить или отключить функцию поиска журнала аудита в Центре & безопасности, чтобы включить или отключить возможность администраторов для поиска журнала аудита.
ms.openlocfilehash: aecd1d47592b9a5e2f134b1d9db9ff203b815b18
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919285"
---
# <a name="turn-audit-log-search-on-or-off"></a><span data-ttu-id="677b4-103">Включение и отключение поиска в журнале аудита</span><span class="sxs-lookup"><span data-stu-id="677b4-103">Turn audit log search on or off</span></span>

<span data-ttu-id="677b4-104">По умолчанию ведение журналов аудита включено для организаций, использующих Microsoft 365 и Office 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="677b4-104">Audit logging is turned on by default for Microsoft 365 and Office 365 enterprise organizations.</span></span> <span data-ttu-id="677b4-105">Сюда также входят организации с подпиской E3/G3 или E5/G5.</span><span class="sxs-lookup"><span data-stu-id="677b4-105">This includes organizations with E3/G3 or E5/G5 subscriptions.</span></span> <span data-ttu-id="677b4-106">При включенном поиске журнала аудита в центре соответствия требованиям действия пользователя и администратора организации записывают в журнал аудита и сохраняются в течение 90 дней и до одного года в зависимости от лицензии, назначенной пользователям.</span><span class="sxs-lookup"><span data-stu-id="677b4-106">When audit log search in the compliance center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days, and up to one year depending on the license assigned to users.</span></span> <span data-ttu-id="677b4-107">Однако у вашей организации могут быть причины, по которой вы не хотите записывать и хранить данные журнала аудита.</span><span class="sxs-lookup"><span data-stu-id="677b4-107">However, your organization may have reasons for not wanting to record and retain audit log data.</span></span> <span data-ttu-id="677b4-108">В этих случаях глобальный администратор может принять решение отключить аудит в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="677b4-108">In those cases, a global admin may decide to turn off auditing in Microsoft 365.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="677b4-109">Если вы отключите поиск журнала аудита в Microsoft 365, вы не сможете использовать API управления Office 365 или Azure Sentinel для доступа к данным аудита для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="677b4-109">If you turn off audit log search in Microsoft 365, you can't use the Office 365 Management Activity API or Azure Sentinel to access auditing data for your organization.</span></span> <span data-ttu-id="677b4-110">Отключение поиска журнала аудита, следуя шагам в этой статье, означает, что результаты не будут возвращены при поиске журнала аудита с помощью Центра соответствия требованиям безопасности & или при запуске **cmdlet Search-UnifiedAuditLog** в Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="677b4-110">Turning off audit log search by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="677b4-111">Это также означает, что журналы аудита не будут доступны через API управления Office 365 или Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="677b4-111">This also means that audit logs won't be available through the Office 365 Management Activity API or Azure Sentinel.</span></span>
  
## <a name="before-you-turn-audit-log-search-on-or-off"></a><span data-ttu-id="677b4-112">Прежде чем включить или отключить поиск журнала аудита</span><span class="sxs-lookup"><span data-stu-id="677b4-112">Before you turn audit log search on or off</span></span>

- <span data-ttu-id="677b4-113">Для того чтобы включить или отключить поиск журналов аудита в организации Microsoft 365, вам необходимо получить роль журналов аудита в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="677b4-113">You have to be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Microsoft 365 organization.</span></span> <span data-ttu-id="677b4-114">По умолчанию эта роль назначена группам ролей управления соответствием требованиям и организации на странице **Permissions** в центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="677b4-114">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="677b4-115">Глобальные администраторы в Microsoft 365 являются членами группы ролей управления организацией в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="677b4-115">Global admins in Microsoft 365 are members of the Organization Management role group in Exchange Online.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="677b4-116">Пользователям должны быть назначены разрешения в Exchange Online, чтобы включить или отключить поиск журнала аудита.</span><span class="sxs-lookup"><span data-stu-id="677b4-116">Users have to be assigned permissions in Exchange Online to turn audit log search on or off.</span></span> <span data-ttu-id="677b4-117">Если назначить пользователям роль журналов аудита на странице **Разрешения** в Центре соответствия требованиям & безопасности, они не смогут включить или отключить поиск журнала аудита.</span><span class="sxs-lookup"><span data-stu-id="677b4-117">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn audit log search on or off.</span></span> <span data-ttu-id="677b4-118">Это потому, что в основном cmdlet является Exchange Online PowerShell cmdlet.</span><span class="sxs-lookup"><span data-stu-id="677b4-118">This is because the underlying cmdlet is an Exchange Online PowerShell cmdlet.</span></span> 
    
- <span data-ttu-id="677b4-119">Пошаговая инструкция по поиску журнала аудита см. в журнале Search [the audit log in the Security & Compliance Center.](search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="677b4-119">For step-by-step instructions on searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> <span data-ttu-id="677b4-120">Дополнительные сведения об API управления Microsoft 365 см. в руб. Начало работы с API управления [Microsoft 365.](/office/office-365-management-api/get-started-with-office-365-management-apis)</span><span class="sxs-lookup"><span data-stu-id="677b4-120">For more information about the Microsoft 365 Management Activity API, see [Get started with Microsoft 365 Management APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

- <span data-ttu-id="677b4-121">Чтобы убедиться, что поиск в журнале аудита включен, можно выполнить следующую команду в Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="677b4-121">To verify that audit log search is turned on, you can run the following command in Exchange Online PowerShell:</span></span>

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

    <span data-ttu-id="677b4-122">Значение свойства  `True`  _UnifiedAuditLogIngestionEnabled_ указывает на то, что поиск журнала аудита включен.</span><span class="sxs-lookup"><span data-stu-id="677b4-122">The value of  `True` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned on.</span></span> 
    
## <a name="turn-on-audit-log-search"></a><span data-ttu-id="677b4-123">Включив поиск журнала аудита</span><span class="sxs-lookup"><span data-stu-id="677b4-123">Turn on audit log search</span></span>

<span data-ttu-id="677b4-124">Если поиск журнала аудита не включен для организации, его можно включить в центре соответствия требованиям или с помощью Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="677b4-124">If audit log search is not turned on for your organization, you can turn it on in the compliance center or by using Exchange Online PowerShell.</span></span> <span data-ttu-id="677b4-125">После включив поиск журнала аудита, может потребоваться несколько часов, прежде чем вы сможете возвращать результаты при поиске журнала аудита.</span><span class="sxs-lookup"><span data-stu-id="677b4-125">It may take several hours after you turn on audit log search before you can return results when you search the audit log.</span></span>
  
### <a name="use-the-compliance-center-to-turn-on-audit-log-search"></a><span data-ttu-id="677b4-126">Используйте центр соответствия требованиям, чтобы включить поиск журналов аудита</span><span class="sxs-lookup"><span data-stu-id="677b4-126">Use the compliance center to turn on audit log search</span></span>

1. <span data-ttu-id="677b4-127">[Перейдите в центр соответствия требованиям и](https://protection.office.com) войдите.</span><span class="sxs-lookup"><span data-stu-id="677b4-127">[Go to the compliance center](https://protection.office.com) and sign in.</span></span>

2. <span data-ttu-id="677b4-128">В центре соответствия требованиям перейдите к **поиску**  >  **журнала аудита поиска.**</span><span class="sxs-lookup"><span data-stu-id="677b4-128">In the compliance center, go to **Search** > **Audit log search**.</span></span>

   <span data-ttu-id="677b4-129">Если в организации не включен поиск журнала аудита, отображается баннер, включающий проверку для записи действий пользователя и администратора.</span><span class="sxs-lookup"><span data-stu-id="677b4-129">If audit log search is not turned on for your organization, a banner is displayed saying that auditing has to be turned on to record user and admin activity.</span></span>

3. <span data-ttu-id="677b4-130">Нажмите **кнопку Включить аудит.**</span><span class="sxs-lookup"><span data-stu-id="677b4-130">Click **Turn on auditing**.</span></span>

    ![Нажмите кнопку Включить аудит](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    <span data-ttu-id="677b4-132">Баннер обновляется, чтобы сказать, что журнал аудита готовится и что вы можете искать действия пользователя и администратора в течение нескольких часов.</span><span class="sxs-lookup"><span data-stu-id="677b4-132">The banner is updated to say the audit log is being prepared and that you can search for user and admin activity in a few hours.</span></span>

### <a name="use-powershell-to-turn-on-audit-log-search"></a><span data-ttu-id="677b4-133">Чтобы включить поиск журнала аудита, используйте PowerShell</span><span class="sxs-lookup"><span data-stu-id="677b4-133">Use PowerShell to turn on audit log search</span></span>

1. [<span data-ttu-id="677b4-134">Подключение к PowerShell Exchange Online</span><span class="sxs-lookup"><span data-stu-id="677b4-134">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)

2. <span data-ttu-id="677b4-135">Запустите следующую команду PowerShell, чтобы включить поиск журнала аудита в Office 365.</span><span class="sxs-lookup"><span data-stu-id="677b4-135">Run the following PowerShell command to turn on audit log search in Office 365.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="677b4-136">Отображается сообщение о том, что для в действие изменения может потребоваться до 60 минут.</span><span class="sxs-lookup"><span data-stu-id="677b4-136">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-audit-log-search"></a><span data-ttu-id="677b4-137">Отключение поиска журнала аудита</span><span class="sxs-lookup"><span data-stu-id="677b4-137">Turn off audit log search</span></span>

<span data-ttu-id="677b4-138">Чтобы отключить поиск журнала аудита, необходимо использовать Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="677b4-138">You have to use Exchange Online PowerShell to turn off audit log search.</span></span>
  
1. [<span data-ttu-id="677b4-139">Подключение к PowerShell Exchange Online</span><span class="sxs-lookup"><span data-stu-id="677b4-139">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)

2. <span data-ttu-id="677b4-140">Запустите следующую команду PowerShell, чтобы отключить поиск журнала аудита.</span><span class="sxs-lookup"><span data-stu-id="677b4-140">Run the following PowerShell command to turn off audit log search.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="677b4-141">Через некоторое время убедитесь, что поиск журнала аудита отключен (отключен).</span><span class="sxs-lookup"><span data-stu-id="677b4-141">After a while, verify that audit log search is turned off (disabled).</span></span> <span data-ttu-id="677b4-142">Это можно сделать двумя способами:</span><span class="sxs-lookup"><span data-stu-id="677b4-142">There are two ways to do this:</span></span>

    - <span data-ttu-id="677b4-143">В Exchange Online PowerShell запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="677b4-143">In Exchange Online PowerShell, run the following command:</span></span>

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      <span data-ttu-id="677b4-144">Значение свойства  `False`  _UnifiedAuditLogIngestionEnabled_ указывает на отключение поиска журнала аудита.</span><span class="sxs-lookup"><span data-stu-id="677b4-144">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned off.</span></span> 

    - <span data-ttu-id="677b4-145">В центре [соответствия требованиям](https://protection.office.com)перейдите к поиску журнала  \> **аудита поиска.**</span><span class="sxs-lookup"><span data-stu-id="677b4-145">In the [compliance center](https://protection.office.com), go to **Search** \> **Audit log search**.</span></span>

      <span data-ttu-id="677b4-146">В баннере отображается надпись о том, что для записи действий пользователя и администратора необходимо включить аудит.</span><span class="sxs-lookup"><span data-stu-id="677b4-146">A banner is displayed saying that auditing has to be turned on in order to record user and admin activity.</span></span>