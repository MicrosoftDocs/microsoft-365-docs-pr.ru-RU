---
title: Атрибуты для политик информационных барьеров
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: Используйте эту статью в качестве справки по различным атрибутам, которые можно использовать в политиках барьера информации.
ms.openlocfilehash: 12acaa4fb8d6bcd6c660381b172703bd178af81f
ms.sourcegitcommit: af7950d9674f0eab3aee03f9afccff9ca2f4709a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40970787"
---
# <a name="attributes-for-information-barrier-policies"></a>Атрибуты для политик информационных барьеров

Некоторые атрибуты в Azure Active Directory можно использовать для сегментирования пользователей. После определения сегментов эти сегменты можно использовать в качестве фильтров для политик барьера данных. Например, вы можете использовать **Отдел** , чтобы определять сегменты пользователей по Отделу в Организации (предполагается, что ни один сотрудник не работает одновременно для двух отделов). 

В этой статье описывается, как использовать атрибуты с барьерами информации, а также список атрибутов, которые можно использовать. Дополнительные сведения о барьерах информации можно найти в следующих ресурсах:
- [Информационные барьеры](information-barriers.md)
- [Определение политик для барьеров информации в Microsoft Teams](information-barriers-policies.md)
- [Изменение (или удаление) политик барьера информации](information-barriers-edit-segments-policies.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a>Использование атрибутов в политиках барьера информационных заданных

Атрибуты, приведенные в этой статье, можно использовать для определения и редактирования сегментов пользователей. Заданные сегменты служат параметрами (называемыми значениями *усерграупфилтер* ) в [политиках барьера информации](information-barriers-policies.md).

1. Определите атрибут, который будет использоваться для определения сегментов. (Обратитесь к разделу [Reference](#reference) в этой статье.)

2. Убедитесь, что учетные записи пользователей имеют значения, заполненные для атрибутов, выбранных на шаге 1. Просмотр сведений об учетной записи пользователя и, при необходимости, изменение учетных записей пользователей для включения значений атрибутов. 

    - Чтобы изменить несколько учетных записей (или с помощью PowerShell для редактирования одной учетной записи), ознакомьтесь со статьей [Настройка свойств учетной записи пользователя с помощью Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell).

    - Чтобы изменить одну учетную запись, ознакомьтесь со статьей [Добавление или обновление данных профиля пользователя с помощью Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).

3. [Определите сегменты с помощью PowerShell](information-barriers-policies.md#define-segments-using-powershell), как показано в следующих примерах:

    |Пример  |Командлет  |
    |---------|---------|
    |Определите сегмент под названием Segment1 с помощью атрибута Department     | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"`        |
    |Определите сегмент с именем Segment с помощью атрибута MemberOf (предположим, что этот атрибут содержит имена групп, например, "Блуеграуп").     | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"`        |
    |Определите сегмент с именем Дайтрадерс, используя от extensionattribute1 (предположим, что этот атрибут содержит заголовки заданий, например "Дайтрадер").|`New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

    > [!TIP]
    > При определении сегментов используйте один и тот же атрибут для всех сегментов. Например, если вы определили некоторые сегменты с помощью *отдела*, определите все сегменты с помощью *отдела*. Не определяйте некоторые сегменты, используя *Отдел* и другие, используя *MemberOf*. Убедитесь, что сегменты не перекрываются; Каждый пользователь должен быть назначен только одному сегменту. 

## <a name="reference"></a>Справка

В следующей таблице перечислены атрибуты, которые можно использовать с барьерами информации.

|Имя свойства Azure Active Directory<br/>(Отображаемое имя LDAP)  |Имя свойства Exchange  |
|---------|---------|
|Управляющ       | Управляющ        |
|Company     |Company         |
|Отдел     |Отдел         |
|От extensionattribute1 |CustomAttribute1  |
|ExtensionAttribute2 |CustomAttribute2  |
|ExtensionAttribute3 |CustomAttribute3  |
|ExtensionAttribute4 |CustomAttribute4  |
|ExtensionAttribute5 |CustomAttribute5  |
|ExtensionAttribute6 |CustomAttribute6  |
|ExtensionAttribute7 |CustomAttribute7  |
|ExtensionAttribute8 |CustomAttribute8  |
|ExtensionAttribute9 |CustomAttribute9  |
|ExtensionAttribute10 |CustomAttribute10  |
|ExtensionAttribute11 |CustomAttribute11  |
|ExtensionAttribute12 |CustomAttribute12  |
|ExtensionAttribute13 |CustomAttribute13  |
|ExtensionAttribute14 |CustomAttribute14  |
|ExtensionAttribute15 |CustomAttribute15  |
|От msexchextensioncustomattribute1 |ExtensionCustomAttribute1 |
|MSExchExtensionCustomAttribute2 |ExtensionCustomAttribute2 |
|MSExchExtensionCustomAttribute3 |ExtensionCustomAttribute3 |
|MSExchExtensionCustomAttribute4 |ExtensionCustomAttribute4 |
|MSExchExtensionCustomAttribute5 |ExtensionCustomAttribute5 |
|MailNickname |Псевдоним |
|фисикалделиверйоффиценаме |Office |
|PostalCode |PostalCode |
|ProxyAddresses |EmailAddresses |
|StreetAddress |StreetAddress |
|TargetAddress |ExternalEmailAddress |
|UsageLocation |UsageLocation |
|UserPrincipalName  |UserPrincipalName  |
|Почта   |WindowsEmailAddress    |
|Описание    |Описание    |
|Групп   |мемберофграуп  |

## <a name="related-topics"></a>Связанные статьи

[Определение политик для барьеров информации в Microsoft Teams](information-barriers-policies.md)

[Устранение проблем с информационными барьерами](information-barriers-troubleshooting.md)

[Информационные барьеры](information-barriers.md)



