---
title: Выбор домена, который будет использоваться при создании групп Microsoft 365
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
- Adm_TOC
search.appverid:
- MET150
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
description: Сведения о том, как выбрать домен для использования при создании групп Microsoft 365 путем настройки политик адресов электронной почты с помощью PowerShell.
ms.openlocfilehash: 5ce0068f1b4562c37b2ccf2b1fb9a928b392a7ee
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686734"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a>Выбор домена, который будет использоваться при создании групп Microsoft 365

В некоторых организациях для разных подразделений используются отдельные домены электронной почты. Вы можете указать, какой домен следует использовать, когда пользователи создают группы Microsoft 365.
  
Если согласно требованиям организации пользователи должны создавать группы в доменах, которые отличаются от обслуживаемого домена организации, используемого по умолчанию, вы можете настроить политики адресов электронной почты (EAP) с помощью PowerShell.

Перед запуском командлетов PowerShell Скачайте и установите модуль, который позволит вам общаться с вашей организацией. Ознакомьтесь со статьей [Подключение к Exchange Online с помощью удаленной оболочки PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=785881).

## <a name="example-scenarios"></a>Примеры сценариев

Предположим, что основной домен вашей организации  Contoso.com. Но обслуживаемым доменом по умолчанию для вашей организации является service.contoso.com. Это означает, что группы будут созданы в service.contoso.com (например, jimsteam@service.contoso.com).
  
Предположим, что в вашей организации также настроены поддомены. Вы хотите, чтобы группы создавались в этих доменах:
  
- students.contoso.com для учащихся
    
- faculty.contoso.com для преподавателей
    
В следующих двух сценариях объясняется, как это можно сделать.

> [!NOTE]
> Когда у вас несколько правила EAP, они оцениваются в порядке приоритета. Значение 1 означает самый высокий приоритет. После совпадения EAP не оцениваются никакие дополнительные проверки и адреса, которые помечаются для группы, в соответствии с соответствующим EAP. > если ни один из правила EAP не отвечает указанным условиям, то Группа будет подготовлена к обслуживаемому домену организации по умолчанию. Ознакомьтесь со статьей [Управление обслуживаемыми доменами в Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428) , чтобы получить подробные сведения о добавлении обслуживаемого домена.
  
### <a name="scenario-1"></a>Сценарий 1

В приведенном ниже примере показано, как подготовить все группы Microsoft 365 в Организации в домене groups.contoso.com.
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a>Сценарий 2

Предположим, вы хотите контролировать, в каких дочерних доменах создаются группы Microsoft 365. Вам нужны указанные ниже группы и пользователи.
  
- Группы, созданные студентами (пользователи, у которых есть **Отдел** " **студенты**") в домене students.Groups.contoso.com. Используйте эту команду:
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- Группы, созданные участниками факультета (пользователи, у которых в качестве **подразделения** **или адреса электронной почты есть Faculty.contoso.com)**) в домене Faculty.Groups.contoso.com. Используйте эту команду:
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- Группы, созданные кем угодно, создаются в домене groups.contoso.com. Используйте эту команду:
    
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

Если ваша организация настроена в гибридном сценарии, изучите [настройку групп microsoft 365 с помощью локальной среды Exchange](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups) , чтобы убедиться, что ваша организация соответствует требованиям для создания групп Microsoft 365. 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a>Дополнительные сведения об использовании групп политик адресов электронной почты:

Помните о сказанном ниже.
  
- Скорость создания групп зависит от количества правил EAP, настроенных в организации.
    
- Администраторы и пользователи также могут изменять домены при создании групп.
    
- Группа пользователей определяется с помощью стандартных запросов (свойств пользователей), которые уже доступны. Изучите [фильтруемые свойства для параметра – RecipientFilter](https://docs.microsoft.com/powershell/exchange/recipientfilter-properties) для поддерживаемых фильтруемых свойств. 
    
- Если не настроить правила EAP для групп, при создании групп будет выбираться обслуживаемый домен, используемый по умолчанию.
    
- Перед удалением обслуживаемого домена необходимо сначала обновить правила EAP, иначе будет невозможно создавать группы.
    
- В организации можно настроить не более 100 политик адресов электронной почты.
    
## <a name="related-articles"></a>Статьи по теме

[Создание группы Microsoft 365 в центре администрирования](https://docs.microsoft.com/microsoft-365/admin/create-groups/create-groups)
