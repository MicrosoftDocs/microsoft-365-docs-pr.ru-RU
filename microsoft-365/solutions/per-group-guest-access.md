---
title: Запрет добавления гостевых пользователей в определенную группу
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
description: Сведения о том, как запретить добавление гостей в определенную группу
ms.openlocfilehash: 91c7560186fb0b954075e9ff9c997b34121951cd
ms.sourcegitcommit: cdf2b8dad7db9e16afd339abaaa5397faf11807c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "48651354"
---
# <a name="prevent-guest-users-from-being-added-to-a-specific-microsoft-365-group-or-microsoft-teams-team"></a>Запрет добавления гостевых пользователей в определенную группу Microsoft 365 или группу Microsoft Teams

Если вы хотите разрешить гостям доступ к большинству групп и Teams, но у вас есть некоторые из них для предотвращения гостевого доступа, вы можете заблокировать гостевой доступ для отдельных групп и Teams. (Блокировка гостевого доступа к группе выполняется путем блокировки гостевого доступа к связанной группе.) Это предотвратит добавление новых гостей, но не удаляет гостей, уже включенных в группу или группу.

Если вы используете метки чувствительности в Организации, рекомендуем использовать их для управления гостевым доступом для отдельных групп. Для получения сведений о том, как это сделать, [используйте метки чувствительности для защиты содержимого в Microsoft Teams, microsoft 365 Groups и сайтов SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites). Это рекомендуемый подход.

## <a name="change-group-settings-using-microsoft-powershell"></a>Изменение параметров группы с помощью Microsoft PowerShell

Вы также можете запретить добавление новых гостей в отдельные группы с помощью PowerShell.

Для изменения параметров гостевого доступа на уровне группы необходимо использовать предварительную версию [Azure Active Directory PowerShell для Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (имя модуля **AzureADPreview**):

- Если вы еще не установили ни одной версии модуля Azure AD PowerShell, см. раздел [Установка модуля Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) и следуйте инструкциям по установке общедоступной предварительной версии.

- Если у вас установлена общедоступная версия 2.0 модуля Azure AD PowerShell (AzureAD), вам требуется удалить ее, выполнив команду `Uninstall-Module AzureAD` в сеансе PowerShell, а затем установить предварительную версию, выполнив команду `Install-Module AzureADPreview`.

- Если вы уже установили предварительную версию, выполните команду `Install-Module AzureADPreview`, чтобы убедиться, что это последняя версия модуля.

> [!NOTE]
> Для выполнения этих команд требуются права глобального администратора. 

Выполните следующий сценарий, указав */<GroupName/>* имя группы, в которую необходимо заблокировать гостевой доступ.

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

Чтобы проверить параметры, выполните следующую команду:

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

Проверка выглядит следующим образом:
    
![Снимок экрана: Окно PowerShell, в котором показано, что для доступа к гостевой группе задано значение false.](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a>Разрешение или блокировка гостевого доступа в зависимости от их домена

Вы можете разрешить или заблокировать доступ для пользователей-гостей, почта которых отправляется с определенного домена. Например, если ваша организация (Contoso) имеет связь с другим предприятием (Fabrikam), вы можете добавить Fabrikam в список разрешений, чтобы пользователи могли добавить этих гостей в свои группы.

Дополнительную информацию можно узнать [в статье разрешение или блокировка приглашений для пользователей B2B из определенных организаций](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).

## <a name="add-guests-to-the-global-address-list"></a>Добавление гостей в глобальный список адресов

По умолчанию гости не отображаются в глобальном списке адресов Exchange. Выполните приведенные ниже действия, чтобы сделать гостей видимым в глобальном списке адресов.

Найдите ObjectID пользователя гостя, выполнив следующие действия:

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

Затем выполните приведенные ниже значения с использованием соответствующих значений для ObjectID, GivenName, фамилия, DisplayName и TelephoneNumber.

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-articles"></a>Статьи по теме

[Управление членством в группах в центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups)
  
[Проверка доступа Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set — AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
