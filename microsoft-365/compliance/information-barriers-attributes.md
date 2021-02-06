---
title: Атрибуты для политик информационных барьеров
description: Эта статья является справочником по атрибутам учетной записи пользователя Azure Active Directory, которые можно использовать для определения сегментов информационных барьеров.
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
ms.openlocfilehash: c45a2733c1fa7cf6d05cff747a9cfcdba1b124cc
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126166"
---
# <a name="attributes-for-information-barrier-policies"></a>Атрибуты для политик информационных барьеров

Некоторые атрибуты в Azure Active Directory можно использовать для сегментации пользователей. После определения сегментов эти сегменты можно использовать в качестве фильтров для политик информационных барьеров. Например, можно использовать  отдел для определения сегментов пользователей по отделам в организации (при условии, что ни один сотрудник не работает для двух отделов одновременно).

В этой статье описывается, как использовать атрибуты с информационными барьерами, а также приводится список атрибутов, которые можно использовать. Дополнительные сведения о информационных барьерах см. в следующих ресурсах:

- [Информационные барьеры](information-barriers.md)
- [Определение политик информационных барьеров в Microsoft Teams](information-barriers-policies.md)
- [Изменение (или удаление) политик информационных барьеров](information-barriers-edit-segments-policies.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a>Использование атрибутов в политиках информационных барьеров

Атрибуты, перечисленные в этой статье, можно использовать для определения или изменения сегментов пользователей. Определенные сегменты служат в качестве параметров (называемых *значениями UserGroupFilter)* в политиках [информационных барьеров.](information-barriers-policies.md)

1. Определите, какой атрибут вы хотите использовать для определения сегментов. (См. раздел [справки](#reference) в этой статье.)

2. Убедитесь, что для учетных записей пользователей заполнены значения атрибутов, выбранных на шаге 1. Просмотр сведений об учетной записи пользователя и при необходимости изменение учетных записей пользователей, включив значения атрибутов. 

    - Чтобы изменить несколько учетных записей (или изменить одну учетную запись с помощью PowerShell), см. статью "Настройка свойств учетной записи пользователя с [помощью PowerShell в Office 365".](/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell)

    - Чтобы изменить одну учетную запись, см. статью "Добавление или обновление сведений профиля пользователя [с помощью Azure Active Directory".](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

3. [Определите сегменты с помощью PowerShell,](information-barriers-policies.md#define-segments-using-powershell)как в следующих примерах:

    |**Пример**|**Командлет**|
    |:----------|:---------|
    | Определение сегмента Segment1 с помощью атрибута Department | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"` |
    | Определите сегмент SegmentA с помощью атрибута MemberOf (предположим, что этот атрибут содержит имена групп, например BlueGroup). | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"` |
    | Определите сегмент DayTraders с помощью ExtensionAttribute1 (предположим, что этот атрибут содержит должности, такие как DayTrader) | `New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

    > [!TIP]
    > При определении сегментов используйте один и тот же атрибут для всех сегментов. Например, если вы определяете некоторые сегменты с помощью *Department,* определите все сегменты с помощью *Department.* Не определяйте некоторые сегменты с помощью *Department,* а другие с *помощью MemberOf.* Убедитесь, что ваши сегменты не перекрываются; каждый пользователь должен быть назначен только одному сегменту.

## <a name="reference"></a>Справочные материалы

В следующей таблице перечислены атрибуты, которые можно использовать с информационными барьерами.

|**Имя свойства Azure Active Directory <br/> (отображаемая имя LDAP)**|**Имя свойства Exchange**|
|:---------------------------------------------------------------|:-------------------------|
| Co | Co |
| Company | Company |
| Department | Department |
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
| UsageLocation | UsageLocation |
| UserPrincipalName | UserPrincipalName |
| Почта | WindowsEmailAddress |
| Описание | Описание |
| MemberOf | MemberOfGroup |

## <a name="resources"></a>Ресурсы

- [Определение политик информационных барьеров в Microsoft Teams](information-barriers-policies.md)
- [Устранение проблем с информационными барьерами](information-barriers-troubleshooting.md)
- [Информационные барьеры](information-barriers.md)
