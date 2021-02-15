---
title: Выбор домена для создания групп Microsoft 365
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
description: Узнайте, как выбрать домен для создания групп Microsoft 365, настроив политики адресов электронной почты с помощью PowerShell.
ms.openlocfilehash: 1e56268c3994b1ac822869d154be826326039bfc
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2020
ms.locfileid: "49612944"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a><span data-ttu-id="33b96-103">Выбор домена для создания групп Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="33b96-103">Choose the domain to use when creating Microsoft 365 groups</span></span>

<span data-ttu-id="33b96-104">В некоторых организациях для разных подразделений используются отдельные домены электронной почты.</span><span class="sxs-lookup"><span data-stu-id="33b96-104">Some organizations use separate email domains to segment different parts of their businesses.</span></span> <span data-ttu-id="33b96-105">Вы можете указать домен, который будет использоваться при создании пользователями групп Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="33b96-105">You can specify which domain should be used when your users create Microsoft 365 groups.</span></span>
  
<span data-ttu-id="33b96-106">Если согласно требованиям организации пользователи должны создавать группы в доменах, которые отличаются от обслуживаемого домена организации, используемого по умолчанию, вы можете настроить политики адресов электронной почты (EAP) с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="33b96-106">If your organization needs users to create their groups in domains other than the default accepted domain of your business, you can allow this by configuring email address policies (EAPs) using PowerShell.</span></span>

<span data-ttu-id="33b96-107">Прежде чем запускать командлеты PowerShell, скачайте и установите модуль, который позволит вам общаться с вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="33b96-107">Before you can run the PowerShell cmdlets, download and install a module that will let you talk to your organization.</span></span> <span data-ttu-id="33b96-108">Проверьте подключение [к Exchange Online с помощью удаленной powerShell.](https://go.microsoft.com/fwlink/p/?LinkId=785881)</span><span class="sxs-lookup"><span data-stu-id="33b96-108">Check out [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=785881).</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="33b96-109">Примеры сценариев</span><span class="sxs-lookup"><span data-stu-id="33b96-109">Example scenarios</span></span>

<span data-ttu-id="33b96-110">Предположим, что основной домен вашей организации  Contoso.com.</span><span class="sxs-lookup"><span data-stu-id="33b96-110">Let's say your business's main domain is Contoso.com.</span></span> <span data-ttu-id="33b96-111">Но обслуживаемым доменом по умолчанию для вашей организации является service.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="33b96-111">But your organization's default accepted domain is service.contoso.com.</span></span> <span data-ttu-id="33b96-112">Это означает, что группы будут созданы в service.contoso.com (например, jimsteam@service.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="33b96-112">This means groups will be created in service.contoso.com (for example, jimsteam@service.contoso.com).</span></span>
  
<span data-ttu-id="33b96-113">Предположим, что в вашей организации также настроены поддомены.</span><span class="sxs-lookup"><span data-stu-id="33b96-113">Let's say you also have sub-domains configured in your organization.</span></span> <span data-ttu-id="33b96-114">Вы также хотите, чтобы группы создавались в этих доменах:</span><span class="sxs-lookup"><span data-stu-id="33b96-114">You want groups to be created in these domains, too:</span></span>
  
- <span data-ttu-id="33b96-115">students.contoso.com для учащихся</span><span class="sxs-lookup"><span data-stu-id="33b96-115">students.contoso.com for students</span></span>
    
- <span data-ttu-id="33b96-116">faculty.contoso.com для преподавателей</span><span class="sxs-lookup"><span data-stu-id="33b96-116">faculty.contoso.com for faculty members</span></span>
    
<span data-ttu-id="33b96-117">В следующих двух сценариях объясняется, как это можно сделать.</span><span class="sxs-lookup"><span data-stu-id="33b96-117">The following two scenarios explain how you would accomplish this.</span></span>

> [!NOTE]
> <span data-ttu-id="33b96-118">При стираемом EAP они оцениваются в порядке приоритета.</span><span class="sxs-lookup"><span data-stu-id="33b96-118">When you have mulitple EAPs, they are evaluated in the order of priority.</span></span> <span data-ttu-id="33b96-119">Значение 1 означает наивысший приоритет.</span><span class="sxs-lookup"><span data-stu-id="33b96-119">A value of 1 means the highest priority.</span></span> <span data-ttu-id="33b96-120">После совпадения EAP не оценивается ни один дополнительный EAP, а адреса, которые помещаются в группе, будут соответствовать EAP.</span><span class="sxs-lookup"><span data-stu-id="33b96-120">Once an EAP matches, no further EAP is evaluated and addresses that gets stamped on the group are as per the matched EAP.</span></span> <span data-ttu-id="33b96-121">> если ни один EAP не соответствует указанным условиям, группа будет подготовка в принятом домене организации по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="33b96-121">> If no EAPs match the specified criteria, then the group gets provisioned in the organization's default accepted domain.</span></span> <span data-ttu-id="33b96-122">Дополнительные сведения о добавлении принятого домена можно найти в под управлением принятых доменов [в Exchange Online.](https://go.microsoft.com/fwlink/p/?LinkId=785428)</span><span class="sxs-lookup"><span data-stu-id="33b96-122">Check out [Manage accepted domains in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428) for details on how to add an accepted domain.</span></span>
  
### <a name="scenario-1"></a><span data-ttu-id="33b96-123">Сценарий 1</span><span class="sxs-lookup"><span data-stu-id="33b96-123">Scenario 1</span></span>

<span data-ttu-id="33b96-124">В следующем примере показано, как подготовка всех групп Microsoft 365 в организации в groups.contoso.com домене.</span><span class="sxs-lookup"><span data-stu-id="33b96-124">The following example shows you how to provision all Microsoft 365 groups in your organization in the groups.contoso.com domain.</span></span>
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a><span data-ttu-id="33b96-125">Сценарий 2</span><span class="sxs-lookup"><span data-stu-id="33b96-125">Scenario 2</span></span>

<span data-ttu-id="33b96-126">Предположим, вы хотите контролировать, в каких под доменах создаются группы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="33b96-126">Let's say you want to control what sub-domains Microsoft 365 groups are created in.</span></span> <span data-ttu-id="33b96-127">Вам нужны указанные ниже группы и пользователи.</span><span class="sxs-lookup"><span data-stu-id="33b96-127">You want:</span></span>
  
- <span data-ttu-id="33b96-128">Группы, созданные учащимися (пользователями, для которых в отделе установлено students.groups.contoso.com домене).  </span><span class="sxs-lookup"><span data-stu-id="33b96-128">Groups created by students (users which have **Department** set to **Students**) in the students.groups.contoso.com domain.</span></span> <span data-ttu-id="33b96-129">Используйте эту команду:</span><span class="sxs-lookup"><span data-stu-id="33b96-129">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- <span data-ttu-id="33b96-130">Группы, созданные преподавателями (пользователями, для которых в отделе установлено **faculty.contoso.com)** в faculty.groups.contoso.com домене. </span><span class="sxs-lookup"><span data-stu-id="33b96-130">Groups created by faculty members (users which have **Department** set to **Faculty or email address contains faculty.contoso.com)**) in the faculty.groups.contoso.com domain.</span></span> <span data-ttu-id="33b96-131">Используйте эту команду:</span><span class="sxs-lookup"><span data-stu-id="33b96-131">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- <span data-ttu-id="33b96-132">Группы, созданные любыми другими, создаются в groups.contoso.com домене.</span><span class="sxs-lookup"><span data-stu-id="33b96-132">Groups created by anyone else are created in the groups.contoso.com domain.</span></span> <span data-ttu-id="33b96-133">Используйте эту команду:</span><span class="sxs-lookup"><span data-stu-id="33b96-133">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a><span data-ttu-id="33b96-134">Изменение политик адресов электронной почты</span><span class="sxs-lookup"><span data-stu-id="33b96-134">Change email address policies</span></span>

<span data-ttu-id="33b96-135">Изменить шаблоны приоритетов или адресов электронной почты для существующей EAP можно с помощью командлета Set-EmailAddressPolicy.</span><span class="sxs-lookup"><span data-stu-id="33b96-135">To change the priority or email address templates for an existing EAP, use the Set-EmailAddressPolicy cmdlet.</span></span>
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

<span data-ttu-id="33b96-136">Изменение EAP не влияет на группы, которые уже были подготовлены.</span><span class="sxs-lookup"><span data-stu-id="33b96-136">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="delete-email-address-policies"></a><span data-ttu-id="33b96-137">Удаление политик адресов электронной почты</span><span class="sxs-lookup"><span data-stu-id="33b96-137">Delete email address policies</span></span>

<span data-ttu-id="33b96-138">Удалить EAP можно с помощью командлета Remove-EmailAddressPolicy.</span><span class="sxs-lookup"><span data-stu-id="33b96-138">To delete an EAP, use the Remove-EmailAddressPolicy cmdlet.</span></span>
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

<span data-ttu-id="33b96-139">Изменение EAP не влияет на группы, которые уже были подготовлены.</span><span class="sxs-lookup"><span data-stu-id="33b96-139">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="hybrid-requirements"></a><span data-ttu-id="33b96-140">Требования к гибридной среде</span><span class="sxs-lookup"><span data-stu-id="33b96-140">Hybrid requirements</span></span>

<span data-ttu-id="33b96-141">Если ваша организация настроена в гибридном сценарии, ознакомьтесь с настройкой групп [Microsoft 365](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups) с локальной гибридной конфигурацией Exchange, чтобы убедиться, что ваша организация соответствует требованиям для создания групп Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="33b96-141">If your organization is configured in a hybrid scenario, check out [Configure Microsoft 365 groups with on-premises Exchange hybrid](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups) to make sure your organization meets the requirements for creating Microsoft 365 groups.</span></span> 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a><span data-ttu-id="33b96-142">Дополнительные сведения об использовании групп политик адресов электронной почты:</span><span class="sxs-lookup"><span data-stu-id="33b96-142">Additional info about using email address policies groups:</span></span>

<span data-ttu-id="33b96-143">Помните о сказанном ниже.</span><span class="sxs-lookup"><span data-stu-id="33b96-143">There are a few more things to know:</span></span>
  
- <span data-ttu-id="33b96-144">Скорость создания групп зависит от количества правил EAP, настроенных в организации.</span><span class="sxs-lookup"><span data-stu-id="33b96-144">How fast groups are created depends on the number of EAPs configured in your organization.</span></span>
    
- <span data-ttu-id="33b96-145">Администраторы и пользователи также могут изменять домены при создании групп.</span><span class="sxs-lookup"><span data-stu-id="33b96-145">Admins and users can also modify domains when they create groups.</span></span>
    
- <span data-ttu-id="33b96-146">Группа пользователей определяется с помощью стандартных запросов (свойств пользователей), которые уже доступны.</span><span class="sxs-lookup"><span data-stu-id="33b96-146">Group of users is determined using the standard queries (User properties) that are already available.</span></span> <span data-ttu-id="33b96-147">Ознакомьтесь [с фильтруемыми свойствами параметра -RecipientFilter](https://docs.microsoft.com/powershell/exchange/recipientfilter-properties) для поддерживаемых фильтруемых свойств.</span><span class="sxs-lookup"><span data-stu-id="33b96-147">Check out [Filterable properties for the -RecipientFilter parameter](https://docs.microsoft.com/powershell/exchange/recipientfilter-properties) for supported filterable properties.</span></span> 
    
- <span data-ttu-id="33b96-148">Если не настроить правила EAP для групп, при создании групп будет выбираться обслуживаемый домен, используемый по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="33b96-148">If you don't configure any EAPs for groups, then the default accepted domain is selected for group creation.</span></span>
    
- <span data-ttu-id="33b96-149">Перед удалением обслуживаемого домена необходимо сначала обновить правила EAP, иначе будет невозможно создавать группы.</span><span class="sxs-lookup"><span data-stu-id="33b96-149">If you remove an accepted domain, you should update the EAPs first, otherwise, group provisioning will be impacted.</span></span>
    
- <span data-ttu-id="33b96-150">В организации можно настроить не более 100 политик адресов электронной почты.</span><span class="sxs-lookup"><span data-stu-id="33b96-150">A maximum limit of 100 email address policies can be configured for an organization.</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="33b96-151">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="33b96-151">Related articles</span></span>

[<span data-ttu-id="33b96-152">Пошаговая пошаговая работа по планированию управления совместной работой</span><span class="sxs-lookup"><span data-stu-id="33b96-152">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="33b96-153">Создание плана управления совместной работой</span><span class="sxs-lookup"><span data-stu-id="33b96-153">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="33b96-154">Создание группы Microsoft 365 в Центре администрирования</span><span class="sxs-lookup"><span data-stu-id="33b96-154">Create an Microsoft 365 group in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/create-groups/create-groups)
