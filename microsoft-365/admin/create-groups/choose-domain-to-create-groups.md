---
title: Выбор домена, используемого при создании групп Office 365
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
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
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
description: 'Сведения о том, как выбрать домен для использования при создании групп Office 365 путем настройки политик адресов электронной почты с помощью PowerShell. '
ms.openlocfilehash: 55fc99cd201e66166e7da164777cfba2f763609c
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42245504"
---
# <a name="choose-the-domain-to-use-when-creating-office-365-groups"></a><span data-ttu-id="2ab59-103">Выбор домена, используемого при создании групп Office 365</span><span class="sxs-lookup"><span data-stu-id="2ab59-103">Choose the domain to use when creating Office 365 Groups</span></span>

 <span data-ttu-id="2ab59-p101">В некоторых организациях для разных подразделений используются отдельные домены электронной почты. Вы можете указать, какой домен следует использовать при создании пользователями групп Office 365.</span><span class="sxs-lookup"><span data-stu-id="2ab59-p101">Some organizations use separate email domains to segment different parts of their businesses. You can specify which domain should be used when your users create Office 365 groups.</span></span>
  
<span data-ttu-id="2ab59-106">Если согласно требованиям организации пользователи должны создавать группы в доменах, которые отличаются от обслуживаемого домена организации, используемого по умолчанию, вы можете настроить политики адресов электронной почты (EAP) с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2ab59-106">If your organization needs users to create their groups in domains other than the default accepted domain of your business, you can allow this by configuring email address policies (EAPs) using PowerShell.</span></span>
  
<span data-ttu-id="2ab59-p102">Для использования командлетов PowerShell скачайте и установите модуль, который позволяет управлять организацией Office 365. См. статью [Подключение к Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=785881).</span><span class="sxs-lookup"><span data-stu-id="2ab59-p102">Before you can run the PowerShell cmdlets, download and install a module that will let you talk to your Office 365 organization. Check out [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=785881).</span></span>
  
## <a name="example-scenarios"></a><span data-ttu-id="2ab59-109">Примеры сценариев</span><span class="sxs-lookup"><span data-stu-id="2ab59-109">Example scenarios</span></span>

<span data-ttu-id="2ab59-110">Предположим, что основной домен вашей организации  Contoso.com.</span><span class="sxs-lookup"><span data-stu-id="2ab59-110">Let's say your business's main domain is Contoso.com.</span></span> <span data-ttu-id="2ab59-111">Но обслуживаемым доменом по умолчанию для вашей организации является service.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="2ab59-111">But your organization's default accepted domain is service.contoso.com.</span></span> <span data-ttu-id="2ab59-112">Это означает, что группы будут созданы в service.contoso.com (например, jimsteam@service.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="2ab59-112">This means groups will be created in service.contoso.com (for example, jimsteam@service.contoso.com).</span></span>
  
<span data-ttu-id="2ab59-113">Предположим, что в вашей организации также настроены поддомены.</span><span class="sxs-lookup"><span data-stu-id="2ab59-113">Let's say you also have sub-domains configured in your organization.</span></span> <span data-ttu-id="2ab59-114">Вы хотите, чтобы группы создавались в этих доменах:</span><span class="sxs-lookup"><span data-stu-id="2ab59-114">You want groups to be created in these domains, too:</span></span>
  
- <span data-ttu-id="2ab59-115">students.contoso.com для учащихся</span><span class="sxs-lookup"><span data-stu-id="2ab59-115">students.contoso.com for students</span></span>
    
- <span data-ttu-id="2ab59-116">faculty.contoso.com для преподавателей</span><span class="sxs-lookup"><span data-stu-id="2ab59-116">faculty.contoso.com for faculty members</span></span>
    
<span data-ttu-id="2ab59-117">В следующих двух сценариях объясняется, как это можно сделать.</span><span class="sxs-lookup"><span data-stu-id="2ab59-117">The following two scenarios explain how you would accomplish this.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2ab59-118">Когда у вас несколько правила EAP, они оцениваются в порядке приоритета.</span><span class="sxs-lookup"><span data-stu-id="2ab59-118">When you have mulitple EAPs, they are evaluated in the order of priority.</span></span> <span data-ttu-id="2ab59-119">Значение 1 означает самый высокий приоритет.</span><span class="sxs-lookup"><span data-stu-id="2ab59-119">A value of 1 means the highest priority.</span></span> <span data-ttu-id="2ab59-120">После совпадения EAP не оцениваются никакие дополнительные проверки и адреса, которые помечаются для группы, в соответствии с соответствующим EAP.</span><span class="sxs-lookup"><span data-stu-id="2ab59-120">Once an EAP matches, no further EAP is evaluated and addresses that gets stamped on the group are as per the matched EAP.</span></span> <span data-ttu-id="2ab59-121">> если ни один из правила EAP не отвечает указанным условиям, то Группа будет подготовлена к обслуживаемому домену организации по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2ab59-121">> If no EAPs match the specified criteria, then the group gets provisioned in the organization's default accepted domain.</span></span> <span data-ttu-id="2ab59-122">Ознакомьтесь со статьей [Управление обслуживаемыми доменами в Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428) , чтобы получить подробные сведения о добавлении обслуживаемого домена.</span><span class="sxs-lookup"><span data-stu-id="2ab59-122">Check out [Manage accepted domains in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428) for details on how to add an accepted domain.</span></span> 
  
### <a name="scenario-1"></a><span data-ttu-id="2ab59-123">Сценарий 1</span><span class="sxs-lookup"><span data-stu-id="2ab59-123">Scenario 1</span></span>

<span data-ttu-id="2ab59-124">В приведенном ниже примере показано, как подготовить группы Office 365 в домене groups.contoso.com вашей организации.</span><span class="sxs-lookup"><span data-stu-id="2ab59-124">The following example shows you how to provision all Office 365 groups in your organization in the groups.contoso.com domain.</span></span>
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a><span data-ttu-id="2ab59-125">Сценарий 2</span><span class="sxs-lookup"><span data-stu-id="2ab59-125">Scenario 2</span></span>

<span data-ttu-id="2ab59-126">Предположим, вы хотите определять, в каких поддоменах создаются группы Office 365.</span><span class="sxs-lookup"><span data-stu-id="2ab59-126">Let's say you want to control what sub-domains Office 365 groups are created in.</span></span> <span data-ttu-id="2ab59-127">Вам нужны указанные ниже группы и пользователи.</span><span class="sxs-lookup"><span data-stu-id="2ab59-127">You want:</span></span>
  
- <span data-ttu-id="2ab59-128">Группы, созданные студентами (пользователи, у которых есть **Отдел** " **студенты**") в домене students.Groups.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="2ab59-128">Groups created by students (users which have **Department** set to **Students**) in the students.groups.contoso.com domain.</span></span> <span data-ttu-id="2ab59-129">Используйте эту команду:</span><span class="sxs-lookup"><span data-stu-id="2ab59-129">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- <span data-ttu-id="2ab59-130">Группы, созданные участниками факультета (пользователи, у которых в качестве **подразделения** **или адреса электронной почты есть Faculty.contoso.com)**) в домене Faculty.Groups.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="2ab59-130">Groups created by faculty members (users which have **Department** set to **Faculty or email address contains faculty.contoso.com)**) in the faculty.groups.contoso.com domain.</span></span> <span data-ttu-id="2ab59-131">Используйте эту команду:</span><span class="sxs-lookup"><span data-stu-id="2ab59-131">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- <span data-ttu-id="2ab59-132">Все остальные пользователи в домене groups.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="2ab59-132">All other users in the groups.contoso.com domain.</span></span> <span data-ttu-id="2ab59-133">Используйте эту команду:</span><span class="sxs-lookup"><span data-stu-id="2ab59-133">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a><span data-ttu-id="2ab59-134">Изменение политик адресов электронной почты</span><span class="sxs-lookup"><span data-stu-id="2ab59-134">Change email address policies</span></span>

<span data-ttu-id="2ab59-135">Изменить шаблоны приоритетов или адресов электронной почты для существующей EAP можно с помощью командлета Set-EmailAddressPolicy.</span><span class="sxs-lookup"><span data-stu-id="2ab59-135">To change the priority or email address templates for an existing EAP, use the Set-EmailAddressPolicy cmdlet.</span></span>
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

<span data-ttu-id="2ab59-136">Изменение EAP не влияет на группы, которые уже были подготовлены.</span><span class="sxs-lookup"><span data-stu-id="2ab59-136">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="delete-email-address-policies"></a><span data-ttu-id="2ab59-137">Удаление политик адресов электронной почты</span><span class="sxs-lookup"><span data-stu-id="2ab59-137">Delete email address policies</span></span>

<span data-ttu-id="2ab59-138">Удалить EAP можно с помощью командлета Remove-EmailAddressPolicy.</span><span class="sxs-lookup"><span data-stu-id="2ab59-138">To delete an EAP, use the Remove-EmailAddressPolicy cmdlet.</span></span>
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

<span data-ttu-id="2ab59-139">Изменение EAP не влияет на группы, которые уже были подготовлены.</span><span class="sxs-lookup"><span data-stu-id="2ab59-139">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="hybrid-requirements"></a><span data-ttu-id="2ab59-140">Требования к гибридной среде</span><span class="sxs-lookup"><span data-stu-id="2ab59-140">Hybrid requirements</span></span>

<span data-ttu-id="2ab59-141">Если в вашей организации используется гибридная среда, прочтите статью [Настройка групп Office 365 в локальном гибридном развертывании Exchange](https://go.microsoft.com/fwlink/p/?LinkId=785430), чтобы убедиться, что ваша организация соответствует требованиям для создания групп Office 365.</span><span class="sxs-lookup"><span data-stu-id="2ab59-141">If your organization is configured in a hybrid scenario, check out [Configure Office 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/p/?LinkId=785430) to make sure your organization meets the requirements for creating Office 365 groups.</span></span> 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a><span data-ttu-id="2ab59-142">Дополнительные сведения об использовании групп политик адресов электронной почты:</span><span class="sxs-lookup"><span data-stu-id="2ab59-142">Additional info about using email address policies groups:</span></span>

<span data-ttu-id="2ab59-143">Помните о сказанном ниже.</span><span class="sxs-lookup"><span data-stu-id="2ab59-143">There are a few more things to know:</span></span>
  
- <span data-ttu-id="2ab59-144">Скорость создания групп зависит от количества правил EAP, настроенных в организации.</span><span class="sxs-lookup"><span data-stu-id="2ab59-144">How fast groups are created depends on the number of EAPs configured in your organization.</span></span>
    
- <span data-ttu-id="2ab59-145">Администраторы и пользователи также могут изменять домены при создании групп.</span><span class="sxs-lookup"><span data-stu-id="2ab59-145">Admins and users can also modify domains when they create groups.</span></span>
    
- <span data-ttu-id="2ab59-p110">Группа пользователей определяется на основе уже существующих стандартных запросов (свойств пользователя). Список поддерживаемых фильтруемых свойств см. в статье [Фильтруемые свойства для параметра -RecipientFilter](https://go.microsoft.com/fwlink/p/?LinkId=785918).</span><span class="sxs-lookup"><span data-stu-id="2ab59-p110">Group of users is determined using the standard queries (User properties) that are already available. Check out [Filterable properties for the -RecipientFilter parameter](https://go.microsoft.com/fwlink/p/?LinkId=785918) for supported filterable pproperties.</span></span> 
    
- <span data-ttu-id="2ab59-148">Если не настроить правила EAP для групп, при создании групп будет выбираться обслуживаемый домен, используемый по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2ab59-148">If you don't configure any EAPs for groups, then the default accepted domain is selected for group creation.</span></span>
    
- <span data-ttu-id="2ab59-149">Перед удалением обслуживаемого домена необходимо сначала обновить правила EAP, иначе будет невозможно создавать группы.</span><span class="sxs-lookup"><span data-stu-id="2ab59-149">If you remove an accepted domain, you should update the EAPs first, otherwise, group provisioning will be impacted.</span></span>
    
- <span data-ttu-id="2ab59-150">В организации можно настроить не более 100 политик адресов электронной почты.</span><span class="sxs-lookup"><span data-stu-id="2ab59-150">A maximum limit of 100 email address policies can be configured for an organization.</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="2ab59-151">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="2ab59-151">Related articles</span></span>

[<span data-ttu-id="2ab59-152">Создание группы Office 365 в Центре администрирования</span><span class="sxs-lookup"><span data-stu-id="2ab59-152">Create an Office 365 group in the admin center</span></span>](create-groups.md)
