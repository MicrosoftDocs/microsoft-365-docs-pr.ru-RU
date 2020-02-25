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
# <a name="choose-the-domain-to-use-when-creating-office-365-groups"></a>Выбор домена, используемого при создании групп Office 365

 В некоторых организациях для разных подразделений используются отдельные домены электронной почты. Вы можете указать, какой домен следует использовать при создании пользователями групп Office 365.
  
Если согласно требованиям организации пользователи должны создавать группы в доменах, которые отличаются от обслуживаемого домена организации, используемого по умолчанию, вы можете настроить политики адресов электронной почты (EAP) с помощью PowerShell.
  
Для использования командлетов PowerShell скачайте и установите модуль, который позволяет управлять организацией Office 365. См. статью [Подключение к Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=785881).
  
## <a name="example-scenarios"></a>Примеры сценариев

Предположим, что основной домен вашей организации  Contoso.com. Но обслуживаемым доменом по умолчанию для вашей организации является service.contoso.com. Это означает, что группы будут созданы в service.contoso.com (например, jimsteam@service.contoso.com).
  
Предположим, что в вашей организации также настроены поддомены. Вы хотите, чтобы группы создавались в этих доменах:
  
- students.contoso.com для учащихся
    
- faculty.contoso.com для преподавателей
    
В следующих двух сценариях объясняется, как это можно сделать.
  
> [!NOTE]
> Когда у вас несколько правила EAP, они оцениваются в порядке приоритета. Значение 1 означает самый высокий приоритет. После совпадения EAP не оцениваются никакие дополнительные проверки и адреса, которые помечаются для группы, в соответствии с соответствующим EAP. > если ни один из правила EAP не отвечает указанным условиям, то Группа будет подготовлена к обслуживаемому домену организации по умолчанию. Ознакомьтесь со статьей [Управление обслуживаемыми доменами в Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428) , чтобы получить подробные сведения о добавлении обслуживаемого домена. 
  
### <a name="scenario-1"></a>Сценарий 1

В приведенном ниже примере показано, как подготовить группы Office 365 в домене groups.contoso.com вашей организации.
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a>Сценарий 2

Предположим, вы хотите определять, в каких поддоменах создаются группы Office 365. Вам нужны указанные ниже группы и пользователи.
  
- Группы, созданные студентами (пользователи, у которых есть **Отдел** " **студенты**") в домене students.Groups.contoso.com. Используйте эту команду:
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- Группы, созданные участниками факультета (пользователи, у которых в качестве **подразделения** **или адреса электронной почты есть Faculty.contoso.com)**) в домене Faculty.Groups.contoso.com. Используйте эту команду:
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- Все остальные пользователи в домене groups.contoso.com. Используйте эту команду:
    
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

Если в вашей организации используется гибридная среда, прочтите статью [Настройка групп Office 365 в локальном гибридном развертывании Exchange](https://go.microsoft.com/fwlink/p/?LinkId=785430), чтобы убедиться, что ваша организация соответствует требованиям для создания групп Office 365. 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a>Дополнительные сведения об использовании групп политик адресов электронной почты:

Помните о сказанном ниже.
  
- Скорость создания групп зависит от количества правил EAP, настроенных в организации.
    
- Администраторы и пользователи также могут изменять домены при создании групп.
    
- Группа пользователей определяется на основе уже существующих стандартных запросов (свойств пользователя). Список поддерживаемых фильтруемых свойств см. в статье [Фильтруемые свойства для параметра -RecipientFilter](https://go.microsoft.com/fwlink/p/?LinkId=785918). 
    
- Если не настроить правила EAP для групп, при создании групп будет выбираться обслуживаемый домен, используемый по умолчанию.
    
- Перед удалением обслуживаемого домена необходимо сначала обновить правила EAP, иначе будет невозможно создавать группы.
    
- В организации можно настроить не более 100 политик адресов электронной почты.
    
## <a name="related-articles"></a>Статьи по теме

[Создание группы Office 365 в Центре администрирования](create-groups.md)
