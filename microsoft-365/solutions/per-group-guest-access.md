---
title: Запретить добавлять гостей в определенную группу
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: Узнайте, как запретить добавлять гостей в определенную группу
ms.openlocfilehash: 1db2055f3e546c05905dbf4c854333387112f06e
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538931"
---
# <a name="prevent-guests-from-being-added-to-a-specific-microsoft-365-group-or-microsoft-teams-team"></a>Запретить добавлять гостей в определенную группу Microsoft 365 или Microsoft Teams группу

Если вы хотите разрешить гостевой доступ большинству групп и групп, но имеете некоторые из них, где необходимо предотвратить гостевой доступ, вы можете заблокировать гостевой доступ для отдельных групп и групп. (Блокировка гостевого доступа к группе делается путем блокировки гостевого доступа к связанной группе.) Это не позволяет добавлять новых гостей, но не удаляет гостей, которые уже находятся в группе или команде.

Если в организации используются метки конфиденциальности, рекомендуется использовать их для управления гостевых доступом на групповой основе. Сведения о том, как это сделать, используйте метки конфиденциальности для защиты контента в Microsoft Teams, Microsoft 365 группах и [SharePoint сайтах.](../compliance/sensitivity-labels-teams-groups-sites.md) Это рекомендуемый подход.

## <a name="change-group-settings-using-microsoft-powershell"></a>Изменение параметров группы с помощью Microsoft PowerShell

Вы также можете предотвратить добавление новых гостей в отдельные группы с помощью PowerShell. (Помните, что связанный с SharePoint веб-сайт группы имеет отдельные элементы управления [гостевых обменов.)](/sharepoint/change-external-sharing-site)

Чтобы изменить параметр гостевого доступа на [групповом уровне,](/powershell/azure/active-directory/install-adv2) необходимо использовать предварительную версию Azure Active Directory PowerShell для Graph (имя модуля **AzureADPreview).**

- Если вы еще не установили ни одной версии модуля Azure AD PowerShell, см. раздел [Установка модуля Azure AD](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview) и следуйте инструкциям по установке общедоступной предварительной версии.

- Если у вас установлена общедоступная версия 2.0 модуля Azure AD PowerShell (AzureAD), вам требуется удалить ее, выполнив команду `Uninstall-Module AzureAD` в сеансе PowerShell, а затем установить предварительную версию, выполнив команду `Install-Module AzureADPreview`.

- Если вы уже установили предварительную версию, выполните команду `Install-Module AzureADPreview`, чтобы убедиться, что это последняя версия модуля.

> [!NOTE]
> Для запуска этих команд необходимо иметь глобальные права администратора. 

Запустите следующий сценарий, изменив имя группы, в которой необходимо */<GroupName/>* заблокировать гостевой доступ.

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

Чтобы проверить параметры, запустите эту команду:

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

Проверка выглядит так:
    
![Снимок экрана окна PowerShell, показывающий, что доступ к гостевой группе был заведомо ложным.](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a>Разрешить или заблокировать гостевой доступ на основе домена

Вы можете разрешить или заблокировать гостей, использующих определенный домен. Например, если ваш бизнес (Contoso) имеет партнерские отношения с другим бизнесом (Fabrikam), вы можете добавить Fabrikam в список "Разрешить", чтобы пользователи могли добавлять этих гостей в свои группы.

Дополнительные сведения см. в дополнительных сведениях: Разрешить или блокировать приглашения пользователям [B2B из определенных организаций.](/azure/active-directory/b2b/allow-deny-list)

## <a name="add-guests-to-the-global-address-list"></a>Добавление гостей в глобальный список адресов

По умолчанию гости не видны в глобальном списке Exchange адресов. Используйте указанные ниже действия, чтобы сделать гостя видимым в глобальном списке адресов.

Найдите объектный объект гостя при запуске:

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

Затем запустите следующие значения, используя соответствующие значения для ObjectID, GivenName, Surname, DisplayName и PhoneNumber.

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-topics"></a>Связанные статьи

[Пошаговая пошаговая работа по планированию управления совместной работой](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Создание плана управления совместной работой](collaboration-governance-first.md)

[Управление членством в Microsoft 365 центре администрирования](../admin/create-groups/add-or-remove-members-from-groups.md)
  
[Azure Active Directory доступа](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](/powershell/module/azuread/set-azureaduser)