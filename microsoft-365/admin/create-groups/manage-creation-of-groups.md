---
title: Управление разрешениями пользователей на создание групп Office 365
f1.keywords:
- NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: get-started-article
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
description: Узнайте, как управлять тем, какие пользователи могут создавать группы Office 365.
ms.openlocfilehash: 1f0d3109d1102c740a9be0b670e618eac982e6e2
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42245465"
---
# <a name="manage-who-can-create-office-365-groups"></a>Управление разрешениями пользователей на создание групп Office 365

  
Благодаря тому, что пользователи могут легко создавать группы Office 365, вам не будет приходиться это делать. Однако вам может потребоваться ограничивать права на создание групп или предоставлять их.
  
В этой статье приведены инструкции по отключению возможности создавать группы **во всех службах Office 365, где они используются**: 
  
- Outlook
    
- SharePoint
    
- Yammer
    
- Microsoft Teams

- Microsoft Stream
    
- StaffHub
    
- Планировщик
    
- PowerBI

- План
    
Можно ограничить создание групп Office 365 членами определенной группы безопасности. Чтобы настроить это, используйте Windows PowerShell. В этой статье рассказывается о необходимых действиях.
  
Действия, описанные в этой статье, не позволят членам определенных ролей создавать группы. Глобальные администраторы Office 365 могут создавать группы с помощью любых средств, таких как центр администрирования Майкрософт 365, планировщик, Teams, Exchange и SharePoint Online. Другие роли могут создавать группы с помощью ограниченных средств, перечисленных ниже.
        
  - Администратор Exchange: центр администрирования Exchange, Azure AD
    
  - Поддержка уровня партнеров 1: центр администрирования Microsoft 365, центр администрирования Exchange, Azure AD
    
  - Поддержка уровня партнеров 2: центр администрирования Microsoft 365, центр администрирования Exchange, Azure AD
    
  - Записи в каталогах: Azure AD

  - Администратор SharePoint: центр администрирования SharePoint, Azure AD
  
  - Администратор службы teams: центр администрирования Teams, Azure AD
  
  - Администратор управления пользователями: центр администрирования Microsoft 365, Yammer, Azure AD
     
Если вы входите в одну из этих ролей, вы можете создать Группы Office 365 для пользователей с ограниченными правами, а затем назначить пользователя владельцем группы. Пользователи с этой ролью могут создавать подключенные группы в Yammer независимо от параметров PowerShell, которые могут препятствовать созданию.

## <a name="licensing-requirements"></a>Требования к лицензированию

Для управления разрешениями групп для следующих людей требуются лицензии Azure AD Premium или Azure AD Basic EDU, назначенные им:

- Администратор, который настраивает эти параметры создания групп
- Члены группы безопасности, которым разрешено создавать группы

Следующим пользователям не нужны лицензии Azure AD Premium или Azure AD Basic EDU:

- Пользователи, являющиеся членами групп Office 365 и у которых нет возможности создавать другие группы.

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-office-365-groups"></a>Шаг 1. Создание группы безопасности для пользователей, которые должны создавать Группы Office 365

Для контроля того, кто может создавать группы, можно использовать только одну группу безопасности в Организации. Но вы можете вложить в нее другие группы безопасности как участников. Например, группой безопасности может быть группа Allow Group Creation, участниками которой являются группы Microsoft Planner Users и Exchange Online Users.

Администраторы из перечисленных выше ролей не должны быть членами этой группы: они сохраняют возможность создавать группы.

> [!IMPORTANT]
> Обязательно используйте **группу безопасности** , чтобы ограничить круг пользователей, которые могут создавать группы. Ее участники не смогут создать группу из SharePoint, так как SharePoint проверяет наличие группы безопасности. 
    
1. В центре администрирования перейдите на страницу <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">группы</a> **группы** \> .

2. Нажмите кнопку **Добавить группу**.

3. Выберите пункт **Безопасность** в качестве типа группы. Запомните имя группы. Он потребуется позже.
  
4. Завершите настройку группы безопасности, Добавление пользователей или других групп безопасности, которые будут иметь возможность создавать группы в Организации.
    
Подробные инструкции приведены в разделе [Создание, изменение и удаление группы безопасности в центре администрирования Microsoft 365](../email/create-edit-or-delete-a-security-group.md).
  
## <a name="step-2-install-the-preview-version-of-the-azure-active-directory-powershell-for-graph"></a>Шаг 2: Установка ознакомительной версии Azure Active Directory PowerShell для Graph

Для выполнения этих процедур требуется предварительная версия Azure Active Directory PowerShell для Graph. Эта версия не будет работать.


> [!IMPORTANT]
> Вы не можете одновременно установить версии Preview и GA на одном компьютере. Вы можете установить модуль в Windows 10, Windows Server 2016.

  
Рекомендуется  *всегда*  следить за актуальностью компонентов: удалите старую версию AzureADPreview или AzureAD и установите последнюю. 
  
1. В строке поиска введите Windows PowerShell.
    
2. Щелкните программу **Windows PowerShell** правой кнопкой мыши и выберите пункт **Запуск от имени администратора**.
    
    ![Откройте PowerShell с помощью команды "Запуск от имени администратора".](../media/52517af8-c7b0-4c8f-b2f3-0f82f9d5ace1.png)
  
2. Проверьте установленный модуль:
    
    ```
    Get-InstalledModule -Name "AzureAD*"
    ```

3. Чтобы удалить предыдущую версию AzureADPreview или AzureAD, выполните следующую команду:
  
    ```
    Uninstall-Module AzureADPreview
    ```

    или
  
    ```
    Uninstall-Module AzureAD
    ```

4. To install the latest version of AzureADPreview, run this command:
  
    ```
    Install-Module AzureADPreview
    ```

    At the message about an untrusted repository, type **Y**. It will take a minute or so for the new module to install. 

Оставьте окно PowerShell открытым для шага 3 ниже.
  
## <a name="step-3-run-powershell-commands"></a>Шаг 3: выполнение команд PowerShell

Скопируйте приведенный ниже скрипт в текстовый редактор, например "Блокнот" или [Windows POWERSHELL ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).

Замените * \<секуритиграупнаме\> * именем группы безопасности, которую вы создали. Пример:

`$GroupName = "Group Creators"`

Сохраните файл как Граупкреаторс. ps1. 

В окне PowerShell перейдите к папке, в которую был сохранен файл (введите "CD <FileLocation>").

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
    $settingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -SearchString $GroupName).objectid
}
 else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

В последней строке сценария отобразятся обновленные параметры:

![This is what your settings will look like when you're done.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

Если в будущем требуется изменить группу безопасности, можно повторно запустить скрипт с именем новой группы безопасности.

Если вы хотите отключить ограничение на создание групп и снова разрешить всем пользователям создавать группы, задайте для параметра $GroupName значение "" и $AllowGroupCreation значение true, а затем повторно запустите сценарий.
    
## <a name="step-4-verify-that-it-works"></a>Шаг 4: Убедитесь, что он работает

1. Войдите в Office 365 с учетной записью пользователя, у которого нет возможности создавать группы. То есть они не являются участниками группы безопасности, созданной или администратором.
    
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
