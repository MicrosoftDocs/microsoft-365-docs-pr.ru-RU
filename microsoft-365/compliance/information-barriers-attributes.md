---
title: Атрибуты для политик информационных барьеров
description: Эта статья является ссылкой на атрибуты Azure Active Directory учетной записи, которые можно использовать для определения сегментов информационного барьера.
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ee410bf455e770087da7999ad2019c17419a8e00
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919735"
---
# <a name="attributes-for-information-barrier-policies"></a>Атрибуты для политик информационных барьеров

Некоторые атрибуты в Azure Active Directory можно использовать для сегментации пользователей. После определения сегментов эти сегменты можно использовать в качестве фильтров для политик информационного барьера. Например, можно использовать **Department** для определения сегментов пользователей по подразделениям в организации (если один сотрудник не работает одновременно для двух отделов).

В этой статье описывается использование атрибутов с информационными барьерами, а также содержится список атрибутов, которые можно использовать. Дополнительные сведения о информационных барьерах см. в следующих ресурсах:

- [Информационные барьеры](information-barriers.md)
- [Определение политик для информационных барьеров в Microsoft Teams](information-barriers-policies.md)
- [Изменение (или удаление) политик информационных барьеров](information-barriers-edit-segments-policies.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a>Использование атрибутов в политиках информационного барьера

Атрибуты, перечисленные в этой статье, можно использовать для определения или редактирования сегментов пользователей. Определенные сегменты служат параметрами (называемыми *значениями UserGroupFilter)* в политиках [информационного барьера.](information-barriers-policies.md)

1. Определите, какой атрибут необходимо использовать для определения сегментов. (См. [раздел Справка](#reference) в этой статье.)

2. Убедитесь, что учетные записи пользователей имеют значения, заполненные для атрибута (ы), выбранного в шаге 1. Просмотр сведений о учетных записях пользователей, а при необходимости изменить учетные записи пользователей, чтобы включить значения атрибутов. 

    - Чтобы изменить несколько учетных записей (или использовать PowerShell для редактирования одной учетной записи), см. в статью Настройка свойств учетной записи пользователей с [помощью Office 365 PowerShell.](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)

    - Чтобы изменить одну учетную запись, см. статью Добавление или обновление сведений о профиле пользователя с [помощью Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

3. [Определите сегменты с помощью PowerShell,](information-barriers-policies.md#define-segments-using-powershell)аналогичные следующим примерам:

    |**Пример**|**Командлет**|
    |:----------|:---------|
    | Определение сегмента Segment1 с помощью атрибута Department | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"` |
    | Определите сегмент SegmentA с помощью атрибута MemberOf (предположим, что этот атрибут содержит имена групп, такие как "BlueGroup") | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"` |
    | Определение сегмента DayTraders с помощью ExtensionAttribute1 (предположим, что этот атрибут содержит названия рабочих мест, такие как "DayTrader") | `New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

    > [!TIP]
    > При определении сегментов используйте один и тот же атрибут для всех сегментов. Например, если вы определяете некоторые сегменты с помощью *Department,* определите все сегменты с помощью *Department*. Не определяйте некоторые сегменты с помощью *Department,* а другие с *помощью MemberOf.* Убедитесь, что сегменты не пересекаются; каждый пользователь должен быть назначен именно одному сегменту.

## <a name="reference"></a>Справочные материалы

В следующей таблице перечислены атрибуты, которые можно использовать с информационными барьерами.

|**Azure Active Directory <br/> свойства (имя отображения LDAP)**|**Exchange имени свойства**|
|:---------------------------------------------------------------|:-------------------------|
| Co | Co |
| Организация | Организация |
| Отдел | Отдел |
| ExtensionAttribute1 | CustomAttribute1 |
| ExtensionAttribute2 | CustomAttribute2 |
| ExtensionAttribute3 | CustomAttribute3 |
| ExtensionAttribute4 | CustomAttribute4 |
| ExtensionAttribute5 | CustomAttribute5 |
| ExtensionAttribute6 | CustomAttribute6 |
| ExtensionAttribute7 | CustomAttribute7 |
| ExtensionAttribute8 | CustomAttribute8 |
| ExtensionAttribute9 | CustomAttribute9 |
| ExtensionAttribute10 | CustomAttribute10 |
| ExtensionAttribute11 | CustomAttribute11 |
| ExtensionAttribute12 | CustomAttribute12 |
| ExtensionAttribute13 | CustomAttribute13 |
| ExtensionAttribute14 | CustomAttribute14 |
| ExtensionAttribute15 | CustomAttribute15 |
| MSExchExtensionCustomAttribute1 | ExtensionCustomAttribute1 |
| MSExchExtensionCustomAttribute2 | ExtensionCustomAttribute2 |
| MSExchExtensionCustomAttribute3 | ExtensionCustomAttribute3 |
| MSExchExtensionCustomAttribute4 | ExtensionCustomAttribute4 |
| MSExchExtensionCustomAttribute5 | ExtensionCustomAttribute5 |
| MailNickname | Alias |
| PhysicalDeliveryOfficeName | Office |
| PostalCode | PostalCode |
| ProxyAddresses | EmailAddresses |
| StreetAddress | StreetAddress |
| TargetAddress | ExternalEmailAddress |
| UseLocation | UseLocation |
| UserPrincipalName | UserPrincipalName |
| Почта | WindowsEmailAddress |
| Описание | Описание |
| MemberOf | MemberOfGroup |

## <a name="resources"></a>Ресурсы

- [Определение политик для информационных барьеров в Microsoft Teams](information-barriers-policies.md)
- [Устранение проблем с информационными барьерами](information-barriers-troubleshooting.md)
- [Информационные барьеры](information-barriers.md)