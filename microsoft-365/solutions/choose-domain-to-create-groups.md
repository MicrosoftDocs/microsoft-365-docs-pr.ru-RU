---
title: Выберите домен, который можно использовать при создании Microsoft 365 групп
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
recommendations: false
description: Узнайте, как выбрать домен, который можно использовать при создании Microsoft 365 групп, настроив политики адресов электронной почты с помощью PowerShell.
ms.openlocfilehash: 4d620c3344f83f56afd05c00d78615331dd413ed
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583152"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a><span data-ttu-id="10f9d-103">Выберите домен, который можно использовать при создании Microsoft 365 групп</span><span class="sxs-lookup"><span data-stu-id="10f9d-103">Choose the domain to use when creating Microsoft 365 groups</span></span>

<span data-ttu-id="10f9d-104">В некоторых организациях для разных подразделений используются отдельные домены электронной почты.</span><span class="sxs-lookup"><span data-stu-id="10f9d-104">Some organizations use separate email domains to segment different parts of their businesses.</span></span> <span data-ttu-id="10f9d-105">Вы можете указать, какой домен следует использовать при создании Microsoft 365 групп.</span><span class="sxs-lookup"><span data-stu-id="10f9d-105">You can specify which domain should be used when your users create Microsoft 365 groups.</span></span>
  
<span data-ttu-id="10f9d-106">Если согласно требованиям организации пользователи должны создавать группы в доменах, которые отличаются от обслуживаемого домена организации, используемого по умолчанию, вы можете настроить политики адресов электронной почты (EAP) с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="10f9d-106">If your organization needs users to create their groups in domains other than the default accepted domain of your business, you can allow this by configuring email address policies (EAPs) using PowerShell.</span></span>

<span data-ttu-id="10f9d-107">Прежде чем запускать командлеты PowerShell, скачайте и установите модуль, который позволит вам поговорить с организацией.</span><span class="sxs-lookup"><span data-stu-id="10f9d-107">Before you can run the PowerShell cmdlets, download and install a module that will let you talk to your organization.</span></span> <span data-ttu-id="10f9d-108">Ознакомьтесь [с Подключение Exchange Online с помощью удаленной PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="10f9d-108">Check out [Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="10f9d-109">Примеры сценариев</span><span class="sxs-lookup"><span data-stu-id="10f9d-109">Example scenarios</span></span>

<span data-ttu-id="10f9d-110">Предположим, что основной домен вашей организации  Contoso.com.</span><span class="sxs-lookup"><span data-stu-id="10f9d-110">Let's say your business's main domain is Contoso.com.</span></span> <span data-ttu-id="10f9d-111">Но обслуживаемым доменом по умолчанию для вашей организации является service.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="10f9d-111">But your organization's default accepted domain is service.contoso.com.</span></span> <span data-ttu-id="10f9d-112">Это означает, что группы будут создаваться в service.contoso.com (например, jimsteam@service.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="10f9d-112">This means groups will be created in service.contoso.com (for example, jimsteam@service.contoso.com).</span></span>
  
<span data-ttu-id="10f9d-113">Предположим, что в вашей организации также настроены поддомены.</span><span class="sxs-lookup"><span data-stu-id="10f9d-113">Let's say you also have sub-domains configured in your organization.</span></span> <span data-ttu-id="10f9d-114">Вы также хотите, чтобы в этих доменах создавались группы:</span><span class="sxs-lookup"><span data-stu-id="10f9d-114">You want groups to be created in these domains, too:</span></span>
  
- <span data-ttu-id="10f9d-115">students.contoso.com для учащихся</span><span class="sxs-lookup"><span data-stu-id="10f9d-115">students.contoso.com for students</span></span>
    
- <span data-ttu-id="10f9d-116">faculty.contoso.com для преподавателей</span><span class="sxs-lookup"><span data-stu-id="10f9d-116">faculty.contoso.com for faculty members</span></span>
    
<span data-ttu-id="10f9d-117">В следующих двух сценариях объясняется, как это можно сделать.</span><span class="sxs-lookup"><span data-stu-id="10f9d-117">The following two scenarios explain how you would accomplish this.</span></span>

> [!NOTE]
> <span data-ttu-id="10f9d-118">Если у вас есть mulitple EAP, они оцениваются в порядке приоритета.</span><span class="sxs-lookup"><span data-stu-id="10f9d-118">When you have mulitple EAPs, they are evaluated in the order of priority.</span></span> <span data-ttu-id="10f9d-119">Значение 1 означает наивысший приоритет.</span><span class="sxs-lookup"><span data-stu-id="10f9d-119">A value of 1 means the highest priority.</span></span> <span data-ttu-id="10f9d-120">После совпадения EAP не будет оцениваться дальнейшая EAP, а адреса, на которые будет напечатан штамп в группе, будут соответствовать EAP.</span><span class="sxs-lookup"><span data-stu-id="10f9d-120">Once an EAP matches, no further EAP is evaluated and addresses that gets stamped on the group are as per the matched EAP.</span></span> <span data-ttu-id="10f9d-121">> Если никакие EAP не соответствуют указанным критериям, группа получает предварительную оценку в принятом по умолчанию домене организации.</span><span class="sxs-lookup"><span data-stu-id="10f9d-121">> If no EAPs match the specified criteria, then the group gets provisioned in the organization's default accepted domain.</span></span> <span data-ttu-id="10f9d-122">Сведения о добавлении принятого домена [Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) в области управления принятыми доменами.</span><span class="sxs-lookup"><span data-stu-id="10f9d-122">Check out [Manage accepted domains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) for details on how to add an accepted domain.</span></span>
  
### <a name="scenario-1"></a><span data-ttu-id="10f9d-123">Сценарий 1</span><span class="sxs-lookup"><span data-stu-id="10f9d-123">Scenario 1</span></span>

<span data-ttu-id="10f9d-124">В следующем примере показано, как Microsoft 365 всех групп организации в groups.contoso.com домене.</span><span class="sxs-lookup"><span data-stu-id="10f9d-124">The following example shows you how to provision all Microsoft 365 groups in your organization in the groups.contoso.com domain.</span></span>
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a><span data-ttu-id="10f9d-125">Сценарий 2</span><span class="sxs-lookup"><span data-stu-id="10f9d-125">Scenario 2</span></span>

<span data-ttu-id="10f9d-126">Предположим, необходимо контролировать, в каких Microsoft 365 создаются под домены.</span><span class="sxs-lookup"><span data-stu-id="10f9d-126">Let's say you want to control what sub-domains Microsoft 365 groups are created in.</span></span> <span data-ttu-id="10f9d-127">Вам нужны указанные ниже группы и пользователи.</span><span class="sxs-lookup"><span data-stu-id="10f9d-127">You want:</span></span>
  
- <span data-ttu-id="10f9d-128">Группы, созданные учащимися (пользователями, которые имеют набор **Department** **для** студентов) в students.groups.contoso.com домене.</span><span class="sxs-lookup"><span data-stu-id="10f9d-128">Groups created by students (users which have **Department** set to **Students**) in the students.groups.contoso.com domain.</span></span> <span data-ttu-id="10f9d-129">Используйте эту команду:</span><span class="sxs-lookup"><span data-stu-id="10f9d-129">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- <span data-ttu-id="10f9d-130">Группы, созданные преподавателями (пользователями, у которых набор отдела на факультет или адрес электронной почты **faculty.contoso.com)** в faculty.groups.contoso.com домене. </span><span class="sxs-lookup"><span data-stu-id="10f9d-130">Groups created by faculty members (users which have **Department** set to **Faculty or email address contains faculty.contoso.com)**) in the faculty.groups.contoso.com domain.</span></span> <span data-ttu-id="10f9d-131">Используйте эту команду:</span><span class="sxs-lookup"><span data-stu-id="10f9d-131">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- <span data-ttu-id="10f9d-132">Группы, созданные кем-либо еще, создаются в groups.contoso.com домене.</span><span class="sxs-lookup"><span data-stu-id="10f9d-132">Groups created by anyone else are created in the groups.contoso.com domain.</span></span> <span data-ttu-id="10f9d-133">Используйте эту команду:</span><span class="sxs-lookup"><span data-stu-id="10f9d-133">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a><span data-ttu-id="10f9d-134">Изменение политик адресов электронной почты</span><span class="sxs-lookup"><span data-stu-id="10f9d-134">Change email address policies</span></span>

<span data-ttu-id="10f9d-135">Изменить шаблоны приоритетов или адресов электронной почты для существующей EAP можно с помощью командлета Set-EmailAddressPolicy.</span><span class="sxs-lookup"><span data-stu-id="10f9d-135">To change the priority or email address templates for an existing EAP, use the Set-EmailAddressPolicy cmdlet.</span></span>
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

<span data-ttu-id="10f9d-136">Изменение EAP не влияет на группы, которые уже были подготовлены.</span><span class="sxs-lookup"><span data-stu-id="10f9d-136">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="delete-email-address-policies"></a><span data-ttu-id="10f9d-137">Удаление политик адресов электронной почты</span><span class="sxs-lookup"><span data-stu-id="10f9d-137">Delete email address policies</span></span>

<span data-ttu-id="10f9d-138">Удалить EAP можно с помощью командлета Remove-EmailAddressPolicy.</span><span class="sxs-lookup"><span data-stu-id="10f9d-138">To delete an EAP, use the Remove-EmailAddressPolicy cmdlet.</span></span>
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

<span data-ttu-id="10f9d-139">Изменение EAP не влияет на группы, которые уже были подготовлены.</span><span class="sxs-lookup"><span data-stu-id="10f9d-139">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="hybrid-requirements"></a><span data-ttu-id="10f9d-140">Требования к гибридной среде</span><span class="sxs-lookup"><span data-stu-id="10f9d-140">Hybrid requirements</span></span>

<span data-ttu-id="10f9d-141">Если ваша организация настроена в гибридном [](/exchange/hybrid-deployment/set-up-microsoft-365-groups) сценарии, ознакомьтесь с настройками Microsoft 365 групп с локальной гибридной Exchange, чтобы убедиться, что организация соответствует требованиям по созданию Microsoft 365 групп.</span><span class="sxs-lookup"><span data-stu-id="10f9d-141">If your organization is configured in a hybrid scenario, check out [Configure Microsoft 365 groups with on-premises Exchange hybrid](/exchange/hybrid-deployment/set-up-microsoft-365-groups) to make sure your organization meets the requirements for creating Microsoft 365 groups.</span></span> 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a><span data-ttu-id="10f9d-142">Дополнительные сведения об использовании групп политик адресов электронной почты:</span><span class="sxs-lookup"><span data-stu-id="10f9d-142">Additional info about using email address policies groups:</span></span>

<span data-ttu-id="10f9d-143">Помните о сказанном ниже.</span><span class="sxs-lookup"><span data-stu-id="10f9d-143">There are a few more things to know:</span></span>
  
- <span data-ttu-id="10f9d-144">Скорость создания групп зависит от количества правил EAP, настроенных в организации.</span><span class="sxs-lookup"><span data-stu-id="10f9d-144">How fast groups are created depends on the number of EAPs configured in your organization.</span></span>
    
- <span data-ttu-id="10f9d-145">Администраторы и пользователи также могут изменять домены при создании групп.</span><span class="sxs-lookup"><span data-stu-id="10f9d-145">Admins and users can also modify domains when they create groups.</span></span>
    
- <span data-ttu-id="10f9d-146">Группа пользователей определяется с помощью уже доступных стандартных запросов (свойств пользователей).</span><span class="sxs-lookup"><span data-stu-id="10f9d-146">Group of users is determined using the standard queries (User properties) that are already available.</span></span> <span data-ttu-id="10f9d-147">Ознакомьтесь с свойствами, которые можно фильтровать [для параметра -RecipientFilter](/powershell/exchange/recipientfilter-properties) для поддерживаемых фильтруемых свойств.</span><span class="sxs-lookup"><span data-stu-id="10f9d-147">Check out [Filterable properties for the -RecipientFilter parameter](/powershell/exchange/recipientfilter-properties) for supported filterable properties.</span></span> 
    
- <span data-ttu-id="10f9d-148">Если не настроить правила EAP для групп, при создании групп будет выбираться обслуживаемый домен, используемый по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="10f9d-148">If you don't configure any EAPs for groups, then the default accepted domain is selected for group creation.</span></span>
    
- <span data-ttu-id="10f9d-149">Перед удалением обслуживаемого домена необходимо сначала обновить правила EAP, иначе будет невозможно создавать группы.</span><span class="sxs-lookup"><span data-stu-id="10f9d-149">If you remove an accepted domain, you should update the EAPs first, otherwise, group provisioning will be impacted.</span></span>
    
- <span data-ttu-id="10f9d-150">В организации можно настроить не более 100 политик адресов электронной почты.</span><span class="sxs-lookup"><span data-stu-id="10f9d-150">A maximum limit of 100 email address policies can be configured for an organization.</span></span>
    
## <a name="related-content"></a><span data-ttu-id="10f9d-151">См. также:</span><span class="sxs-lookup"><span data-stu-id="10f9d-151">Related content</span></span>

<span data-ttu-id="10f9d-152">[Пошаговая работа по планированию управления совместной](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step) работой (статья)</span><span class="sxs-lookup"><span data-stu-id="10f9d-152">[Collaboration governance planning step-by-step](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step) (article)</span></span>

<span data-ttu-id="10f9d-153">[Создание плана управления совместной работой](collaboration-governance-first.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="10f9d-153">[Create your collaboration governance plan](collaboration-governance-first.md) (article)</span></span>

<span data-ttu-id="10f9d-154">[Создание группы Microsoft 365 в центре администрирования](../admin/create-groups/create-groups.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="10f9d-154">[Create an Microsoft 365 group in the admin center](../admin/create-groups/create-groups.md) (article)</span></span>