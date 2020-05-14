---
title: Управление пользователями, которые могут создавать группы
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
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
- MSP160
- MST160
- MET150
- MOE150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Узнайте, как определять, какие пользователи могут создавать группы Microsoft 365.
ms.openlocfilehash: 7a699a01687aec47fd39ce108c5a8c7a888afe65
ms.sourcegitcommit: 98782ee4497d72232462c51a3071fae313282980
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44222387"
---
# <a name="manage-who-can-create-groups"></a>Управление пользователями, которые могут создавать группы

  
Так как пользователям очень легко создавать группы Microsoft 365, вы не инундатед с запросами на их создание от имени других пользователей. Однако вам может потребоваться ограничивать права на создание групп или предоставлять их.
  
В этой статье объясняется, как отключить возможность создания групп во всех службах Microsoft 365, использующих группы, в том числе:
  
- Outlook
    
- SharePoint
    
- Yammer
    
- Microsoft Teams

- Microsoft Stream
    
- StaffHub
    
- Планировщик
    
- PowerBI

- План
    
Вы можете ограничить создание групп Microsoft 365 членами определенной группы безопасности. Чтобы настроить это, используйте Windows PowerShell. В этой статье рассказывается о необходимых действиях.
  
Действия, описанные в этой статье, не позволят членам определенных ролей создавать группы. Глобальные администраторы могут создавать группы с помощью любых средств, таких как центр администрирования Microsoft 365, планировщик, Teams, Exchange и SharePoint Online. Другие роли могут создавать группы с помощью ограниченных средств, перечисленных ниже.
        
  - Администратор Exchange: центр администрирования Exchange, Azure AD
    
  - Поддержка уровня партнеров 1: центр администрирования Microsoft 365, центр администрирования Exchange, Azure AD
    
  - Поддержка уровня партнеров 2: центр администрирования Microsoft 365, центр администрирования Exchange, Azure AD
    
  - Записи в каталогах: Azure AD

  - Администратор SharePoint: центр администрирования SharePoint, Azure AD
  
  - Администратор службы teams: центр администрирования Teams, Azure AD
  
  - Администратор управления пользователями: центр администрирования Microsoft 365, Yammer, Azure AD
     
Если вы являетесь участником одной из этих ролей, вы можете создать группы Microsoft 365 для пользователей с ограниченным доступом, а затем назначить пользователя владельцем группы. Пользователи с этой ролью могут создавать подключенные группы в Yammer независимо от параметров PowerShell, которые могут препятствовать созданию.

## <a name="licensing-requirements"></a>Требования к лицензированию

Для управления разрешениями групп для следующих людей требуются лицензии Azure AD Premium или Azure AD Basic EDU, назначенные им:

- Администратор, который настраивает эти параметры создания групп
- Члены группы безопасности, которым разрешено создавать группы

> [!NOTE]
> Дополнительные сведения о назначении лицензий Azure можно найти [в статье назначение и удаление лицензий на портале Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) .

Следующим пользователям не нужны лицензии Azure AD Premium или Azure AD Basic EDU:

- Пользователи, являющиеся членами групп Microsoft 365 и у которых нет возможности создавать другие группы.

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-microsoft-365-groups"></a>Шаг 1: создание группы безопасности для пользователей, которым требуется создавать группы Microsoft 365

Для контроля того, кто может создавать группы, можно использовать только одну группу безопасности в Организации. Но вы можете вложить в нее другие группы безопасности как участников. Например, группой безопасности может быть группа Allow Group Creation, участниками которой являются группы Microsoft Planner Users и Exchange Online Users.

Администраторы из перечисленных выше ролей не должны быть членами этой группы: они сохраняют возможность создавать группы.

> [!IMPORTANT]
> Обязательно используйте **группу безопасности** , чтобы ограничить круг пользователей, которые могут создавать группы. Если вы попытаетесь использовать группу Microsoft 365, участники не смогут создать группу из SharePoint, так как она проверяет группу безопасности. 
    
1. В центре администрирования перейдите на **Groups** \> страницу <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">группы</a> группы.

2. Нажмите кнопку **Добавить группу**.

3. Выберите пункт **Безопасность** в качестве типа группы. Запомните имя группы. Он потребуется позже.
  
4. Завершите настройку группы безопасности, Добавление пользователей или других групп безопасности, которые будут иметь возможность создавать группы в Организации.
    
Подробные инструкции приведены в разделе [Создание, изменение и удаление группы безопасности в центре администрирования Microsoft 365](../email/create-edit-or-delete-a-security-group.md).
 
## <a name="step-2-run-powershell-commands"></a>Шаг 2. Запуск команд PowerShell

Для изменения параметров гостевого доступа на уровне группы необходимо использовать предварительную версию [Azure Active Directory PowerShell для Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (имя модуля **AzureADPreview**):

- Если вы еще не установили ни одной версии модуля Azure AD PowerShell, см. раздел [Установка модуля Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) и следуйте инструкциям по установке общедоступной предварительной версии.

- Если у вас установлена общедоступная версия 2.0 модуля Azure AD PowerShell (AzureAD), вам требуется удалить ее, выполнив команду `Uninstall-Module AzureAD` в сеансе PowerShell, а затем установить предварительную версию, выполнив команду `Install-Module AzureADPreview`.

- Если вы уже установили предварительную версию, выполните команду `Install-Module AzureADPreview`, чтобы убедиться, что это последняя версия модуля.



Скопируйте приведенный ниже скрипт в текстовый редактор, например "Блокнот" или [Windows POWERSHELL ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).

Замените * \< секуритиграупнаме \> * именем группы безопасности, которую вы создали. Например:

`$GroupName = "Group Creators"`

Сохраните файл как Граупкреаторс. ps1. 

В окне PowerShell перейдите к папке, в которую был сохранен файл (введите "CD <FileLocation> ").

Выполните сценарий, введя следующую команду:

`.\GroupCreators.ps1`

После появления соответствующего запроса [Войдите в систему с учетной записью администратора](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) .

```PowerShell
$GroupName = "<SecurityGroupName>"
$AllowGroupCreation = "False"

Connect-AzureAD

$settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
if(!$settingsObjectID)
{
      $template = Get-AzureADDirectorySettingTemplate | Where-object {$_.displayname -eq "group.unified"}
    $settingsCopy = $template.CreateDirectorySetting()
    New-AzureADDirectorySetting -DirectorySetting $settingsCopy
    $settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
}

$settingsCopy = Get-AzureADDirectorySetting -Id $settingsObjectID
$settingsCopy["EnableGroupCreation"] = $AllowGroupCreation

if($GroupName)
{
    $settingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -Filter "DisplayName eq '$GroupName'").objectId
}
 else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

В последней строке сценария отобразятся обновленные параметры:

![This is what your settings will look like when you're done.](../../media/952cd982-5139-4080-9add-24bafca0830c.png)

Если в будущем требуется изменить группу безопасности, можно повторно запустить скрипт с именем новой группы безопасности.

Если вы хотите отключить ограничение на создание групп и снова разрешить всем пользователям создавать группы, задайте для параметра $GroupName значение "" и $AllowGroupCreation значение true, а затем повторно запустите сценарий.
    
## <a name="step-4-verify-that-it-works"></a>Шаг 4: Убедитесь, что он работает

Для вступления изменений в силу может потребоваться 30 минут или более. Вы можете проверить новые параметры, выполнив следующие действия:

1. Войдите с помощью учетной записи пользователя, у которого нет возможности создавать группы. То есть они не являются участниками группы безопасности, созданной или администратором.
    
2. Выберите плитку **планировщика** . 
    
3. В планировщике выберите **новый план** в левой области навигации, чтобы создать план. 
  
4. Следует получить сообщение о том, что планирование и создание групп отключены.

Повторите ту же процедуру с членом группы безопасности.

> [!NOTE]
> Если участники группы безопасности не могут создавать группы, убедитесь, что они не блокируются с помощью [политики почтовых ящиков OWA](https://go.microsoft.com/fwlink/?linkid=852135).
    
## <a name="related-articles"></a>Статьи по теме

[Начало работы с Office 365 PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[Настройка управления группами самостоятельных служб в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[Set-ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy).

[Командлеты Azure Active Directory для настройки параметров группы](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
