---
title: Управление гостевым доступом в группах Microsoft 365
ms.reviewer: arvaradh
f1.keywords: NOCSH
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
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: Узнайте, как добавлять гостей в группу Microsoft 365, просматривать гостевых пользователей и использовать PowerShell для управления гостевым доступом.
ms.openlocfilehash: a56d9599824ac1436c6f875661bcd573c1f6b1ca
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204747"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>Управление гостевым доступом в группах Microsoft 365

По умолчанию для вашей организации включен гостевой доступ для групп Microsoft 365. Администраторы могут контролировать, разрешено ли гостевой доступ к группам для всей организации или для отдельных групп.

Когда она включена, участники группы могут приглашать гостевых пользователей в группу Microsoft 365 с помощью Outlook в Интернете. Приглашения отправляются владельцу группы для утверждения.

После утверждения пользователь-гость добавляется в каталог и группу.

> [!Note]
> Сети Yammer Enterprise, которые находятся в собственном режиме или в [географическом формате ЕС](https://go.microsoft.com/fwlink/?linkid=2107357) , не поддерживают гостевые сети.
> Microsoft 365 подключенные группы Yammer в настоящее время не поддерживают гостевой доступ, но вы можете создавать неподключенные внешние группы в сети Yammer. Инструкции по [созданию и управлению внешними группами в Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) .

Гостевой доступ в группах часто используется в составе более широкого сценария, включающего SharePoint или Teams. Эти службы имеют собственные параметры общего доступа к гостям. Для получения полных инструкций по настройке общего доступа к гостевым компьютерам в группах, SharePoint и Teams, ознакомьтесь со статьей:

- [Совместная работа с гостями на сайте](../../solutions/collaborate-in-site.md)
- [Совместная работа с гостями в команде](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>Управление группами гостевого доступа

Если вы хотите включить или отключить гостевой доступ в группах, это можно сделать в центре администрирования Microsoft 365.

1. В центре администрирования перейдите в раздел **Показать все** \> **Параметры** \> **организационных параметров** и на вкладке **службы** выберите пункт **Microsoft 365 группы**.
  
2. На странице " **группы Microsoft 365** " выберите, следует ли разрешить пользователям, не входящим в организацию, получать доступ к ресурсам группы или разрешить владельцам групп добавлять людей вне Организации в группы.

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>Добавление гостей в группу Microsoft 365 из центра администрирования

Если гость уже существует в вашем каталоге, вы можете добавить их в свои группы из центра администрирования Microsoft 365.
  
1. В центре администрирования перейдите на **Groups**  >  страницу**группы** группы.
  
2. Щелкните группу, в которую требуется добавить гостя, и выберите **Просмотреть все и управлять участниками** на вкладке **Участники** . 
  
4. Нажмите кнопку **Добавить участников**и выберите имя гостя, которого вы хотите добавить.
    
5. Нажмите **Save** (Сохранить).

Если вы хотите добавить гостя в каталог напрямую, вы можете [Добавить пользователей службы совместной работы Azure Active Directory на портале Azure](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).

Если вы хотите изменить любую информацию гостя, вы можете [Добавить или обновить сведения о профиле пользователя с помощью Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).
  
## <a name="block-guest-users-from-a-specific-group"></a>Блокировка гостевых пользователей из определенной группы

Если вы хотите разрешить гостевой доступ к большинству групп, но если вы хотите запретить гостевой доступ, вы можете заблокировать гостевой доступ для отдельных групп с помощью Microsoft PowerShell.

Для изменения параметров гостевого доступа на уровне группы необходимо использовать предварительную версию [Azure Active Directory PowerShell для Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (имя модуля **AzureADPreview**):

- Если вы еще не установили ни одной версии модуля Azure AD PowerShell, см. раздел [Установка модуля Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) и следуйте инструкциям по установке общедоступной предварительной версии.

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
    
![Снимок экрана: Окно PowerShell, в котором показано, что для доступа к гостевой группе задано значение false.](../../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a>Разрешение или блокировка гостевого доступа в зависимости от их домена

Вы можете разрешить или заблокировать доступ для пользователей-гостей, почта которых отправляется с определенного домена. Например, если ваша организация (Contoso) имеет связь с другим предприятием (Fabrikam), вы можете добавить Fabrikam в список разрешений, чтобы пользователи могли добавить этих гостей в свои группы.

Дополнительную информацию можно узнать [в статье разрешение или блокировка приглашений для пользователей B2B из определенных организаций](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).

## <a name="add-guests-to-the-global-address-list"></a>Добавление гостей в глобальный список адресов

По умолчанию гости не отображаются в глобальном списке адресов Exchange. Выполните приведенные ниже действия, чтобы сделать гостей видимым в глобальном списке адресов. Убедитесь, что гость отображается в центре администрирования Exchange Online. Для отображения новых гостей может потребоваться некоторое время после добавления.

Найдите ObjectID пользователя гостя, выполнив следующие действия:

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

Затем выполните приведенные ниже значения с использованием соответствующих значений для ObjectID, GivenName, фамилия, DisplayName и TelephoneNumber.

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-articles"></a>Связанные статьи

[Управление членством в группах в центре администрирования Microsoft 365](add-or-remove-members-from-groups.md)
  
[Проверка доступа Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set — AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
