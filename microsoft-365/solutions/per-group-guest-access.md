---
title: Запретить добавление гостей в определенную группу
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
description: Узнайте, как запретить гостям добавляться в определенную группу
ms.openlocfilehash: 8bee26bf5ec323536ca1ac6f25ce96927634cee7
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49660052"
---
# <a name="prevent-guests-from-being-added-to-a-specific-microsoft-365-group-or-microsoft-teams-team"></a>Запретить гостям добавляться в определенную группу Microsoft 365 или команду Microsoft Teams

Если вы хотите разрешить гостевой доступ для большинства групп и команд, но хотите запретить гостевой доступ, вы можете заблокировать гостевой доступ для отдельных групп и команд. (Блокировка гостевого доступа к команде делается путем блокирования гостевого доступа к связанной группе.) Это предотвращает добавление новых гостей, но не удаляет гостей, которые уже находятся в группе или команде.

Если в вашей организации используются метки конфиденциальности, мы рекомендуем использовать их для управления гостевом доступом на уровне группы. Сведения о том, как это сделать, можно получить с помощью меток конфиденциальности для защиты контента в Microsoft Teams, группах [Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)и на сайтах SharePoint. Это рекомендуемый подход.

## <a name="change-group-settings-using-microsoft-powershell"></a>Изменение параметров группы с помощью Microsoft PowerShell

Вы также можете запретить добавление новых гостей в отдельные группы с помощью PowerShell. (Помните, что связанный с командой сайт SharePoint имеет отдельные [элементы управления гостевых общий доступ.)](https://docs.microsoft.com/sharepoint/change-external-sharing-site)

Чтобы изменить параметр гостевого доступа на уровне группы, необходимо использовать предварительную версию [Azure Active Directory PowerShell для Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (имя модуля **AzureADPreview):**

- Если вы еще не установили ни одной версии модуля Azure AD PowerShell, см. раздел [Установка модуля Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) и следуйте инструкциям по установке общедоступной предварительной версии.

- Если у вас установлена общедоступная версия 2.0 модуля Azure AD PowerShell (AzureAD), вам требуется удалить ее, выполнив команду `Uninstall-Module AzureAD` в сеансе PowerShell, а затем установить предварительную версию, выполнив команду `Install-Module AzureADPreview`.

- Если вы уже установили предварительную версию, выполните команду `Install-Module AzureADPreview`, чтобы убедиться, что это последняя версия модуля.

> [!NOTE]
> Для запуска этих команд необходимо иметь права глобального администратора. 

Запустите следующий сценарий, заменив имя группы, в которой необходимо */<GroupName/>* заблокировать гостевой доступ.

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

Чтобы проверить параметры, запустите команду:

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

Проверка выглядит так:
    
![Screenshot of PowerShell window showing that guest group access has been set to false.](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a>Разрешение или блокировка гостевого доступа в зависимости от домена

Вы можете разрешить или заблокировать гостей, использующих определенный домен. Например, если ваш бизнес (Contoso) имеет партнерство с другим предприятием (Fabrikam), вы можете добавить Fabrikam в список "Разрешить", чтобы пользователи могли добавлять этих гостей в свои группы.

Дополнительные сведения см. в сведениях о том, как разрешить или заблокировать приглашения пользователям [B2B из определенных организаций.](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)

## <a name="add-guests-to-the-global-address-list"></a>Добавление гостей в глобальный список адресов

По умолчанию гости не видны в глобальном списке адресов Exchange. С помощью указанных ниже действий можно сделать гостя видимым в глобальном списке адресов.

Найдите ObjectID гостя, выдав:

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

Затем запустите следующее, используя соответствующие значения для ObjectID, GivenName, Surname, DisplayName и TelephoneNumber.

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-topics"></a>Связанные статьи

[Пошаговая пошаговая работа по планированию управления совместной работой](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Создание плана управления совместной работой](collaboration-governance-first.md)

[Управление членством в группах в Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups)
  
[Проверки доступа Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
