---
title: Выберите домен, который можно использовать при создании групп Microsoft 365
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
description: Узнайте, как выбрать домен, который можно использовать при создании групп Microsoft 365, настроив политики адресов электронной почты с помощью PowerShell.
ms.openlocfilehash: 4908d5bd58ca6d0fbb50151983ddb459f0732284
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904688"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a>Выберите домен, который можно использовать при создании групп Microsoft 365

В некоторых организациях для разных подразделений используются отдельные домены электронной почты. Вы можете указать, какой домен следует использовать при создании пользователями групп Microsoft 365.
  
Если согласно требованиям организации пользователи должны создавать группы в доменах, которые отличаются от обслуживаемого домена организации, используемого по умолчанию, вы можете настроить политики адресов электронной почты (EAP) с помощью PowerShell.

Прежде чем запускать командлеты PowerShell, скачайте и установите модуль, который позволит вам поговорить с организацией. Проверьте Подключение [к Exchange Online с помощью удаленной PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

## <a name="example-scenarios"></a>Примеры сценариев

Предположим, что основной домен вашей организации  Contoso.com. Но обслуживаемым доменом по умолчанию для вашей организации является service.contoso.com. Это означает, что группы будут создаваться в service.contoso.com (например, jimsteam@service.contoso.com).
  
Предположим, что в вашей организации также настроены поддомены. Вы также хотите, чтобы в этих доменах создавались группы:
  
- students.contoso.com для учащихся
    
- faculty.contoso.com для преподавателей
    
В следующих двух сценариях объясняется, как это можно сделать.

> [!NOTE]
> Если у вас есть mulitple EAP, они оцениваются в порядке приоритета. Значение 1 означает наивысший приоритет. После совпадения EAP не будет оцениваться дальнейшая EAP, а адреса, на которые будет напечатан штамп в группе, будут соответствовать EAP. > Если никакие EAP не соответствуют указанным критериям, группа получает предварительную оценку в принятом по умолчанию домене организации. Сведения о добавлении принятого домена можно найти в [Exchange Online.](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)
  
### <a name="scenario-1"></a>Сценарий 1

В следующем примере показана подготовка всех групп Microsoft 365 в организации в groups.contoso.com домене.
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a>Сценарий 2

Предположим, необходимо контролировать, в каких под доменах созданы группы Microsoft 365. Вам нужны указанные ниже группы и пользователи.
  
- Группы, созданные учащимися (пользователями, которые имеют набор **Department** **для** студентов) в students.groups.contoso.com домене. Используйте эту команду:
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- Группы, созданные преподавателями (пользователями, у которых набор отдела на факультет или адрес электронной почты **faculty.contoso.com)** в faculty.groups.contoso.com домене.  Используйте эту команду:
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- Группы, созданные кем-либо еще, создаются в groups.contoso.com домене. Используйте эту команду:
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a>Изменение политик адресов электронной почты

Изменить шаблоны приоритетов или адресов электронной почты для существующей EAP можно с помощью командлета Set-EmailAddressPolicy.
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

Изменение EAP не влияет на группы, которые уже были подготовлены.
  
## <a name="delete-email-address-policies"></a>Удаление политик адресов электронной почты

Удалить EAP можно с помощью командлета Remove-EmailAddressPolicy.
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

Изменение EAP не влияет на группы, которые уже были подготовлены.
  
## <a name="hybrid-requirements"></a>Требования к гибридной среде

Если ваша организация настроена в гибридном сценарии, ознакомьтесь с настройками групп [Microsoft 365](/exchange/hybrid-deployment/set-up-microsoft-365-groups) с локальной гибридной версией Exchange, чтобы убедиться, что организация соответствует требованиям для создания групп Microsoft 365. 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a>Дополнительные сведения об использовании групп политик адресов электронной почты:

Помните о сказанном ниже.
  
- Скорость создания групп зависит от количества правил EAP, настроенных в организации.
    
- Администраторы и пользователи также могут изменять домены при создании групп.
    
- Группа пользователей определяется с помощью уже доступных стандартных запросов (свойств пользователей). Ознакомьтесь с свойствами, которые можно фильтровать [для параметра -RecipientFilter](/powershell/exchange/recipientfilter-properties) для поддерживаемых фильтруемых свойств. 
    
- Если не настроить правила EAP для групп, при создании групп будет выбираться обслуживаемый домен, используемый по умолчанию.
    
- Перед удалением обслуживаемого домена необходимо сначала обновить правила EAP, иначе будет невозможно создавать группы.
    
- В организации можно настроить не более 100 политик адресов электронной почты.
    
## <a name="related-articles"></a>Статьи по теме

[Пошаговая пошаговая работа по планированию управления совместной работой](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Создание плана управления совместной работой](collaboration-governance-first.md)

[Создание группы Microsoft 365 в центре администрирования](../admin/create-groups/create-groups.md)