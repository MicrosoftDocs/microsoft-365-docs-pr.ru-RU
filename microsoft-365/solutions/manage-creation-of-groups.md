---
title: Управление разрешениями пользователей на создание групп Microsoft 365
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
recommendations: false
description: Узнайте, как управлять, какие пользователи могут создавать Microsoft 365 группы.
ms.openlocfilehash: 19a106d255708f4b1df8f798219ea7ea778bbef3
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539183"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a>Управление разрешениями пользователей на создание групп Microsoft 365

По умолчанию все пользователи могут создавать Microsoft 365 группы. Это рекомендуемый подход, так как он позволяет пользователям приступить к совместной совместной работу без необходимости оказания ИТ-помощи.

Если для бизнеса требуется ограничить пользователей, которые могут создавать группы, Microsoft 365 групп можно ограничить членами определенной Microsoft 365 группы или группы безопасности.

Если вы беспокоите пользователей, создав группы или группы, которые не соответствуют вашим бизнес-стандартам, подумайте о том, чтобы пользователи завершили учебный курс, а затем добавили их в группу разрешенных пользователей.

Когда вы ограничиваете, кто может создать группу, это влияет на все службы, которые полагаются на группы для доступа, в том числе:

- Outlook
- SharePoint
- Yammer
- Microsoft Teams
- Microsoft Stream
- Планировщик
- Power BI (классический)
- Project веб/дорожная карта

Действия в этой статье не будут препятствовать созданию групп членами определенных ролей. Office 365 Глобальные администраторы могут создавать группы через центр администрирования Microsoft 365, планировщик, Exchange и SharePoint Online. Другие роли могут создавать группы с помощью ограниченных средств, перечисленных ниже.

- Exchange Администратор: Exchange центр администрирования, Azure AD
- Поддержка уровня 1 для партнеров: центр администрирования Microsoft 365, центр администрирования Exchange, Azure AD
- Поддержка уровня партнера 2: Microsoft 365 центра администрирования, Exchange центра администрирования, Azure AD
- Авторы каталогов: Azure AD
- SharePoint Администратор: SharePoint администрирования, Azure AD
- Teams Администратор службы: Teams Центр администрирования, Azure AD
- Администратор пользователя: Microsoft 365 центр администрирования, Azure AD

Если вы входите в одну из этих ролей, вы можете создать Microsoft 365 групп для пользователей с ограниченным доступом, а затем назначить пользователя владельцем группы.

## <a name="licensing-requirements"></a>Требования к лицензированию

Для управления созданием групп нужны лицензии Azure AD Premium или лицензии Azure AD Basic EDU:

- Администратор, который настраивает эти параметры создания группы
- Члены группы, которым разрешено создавать группы

> [!NOTE]
> Дополнительные сведения о назначении лицензий Azure [см.](/azure/active-directory/fundamentals/license-users-groups) в Azure Active Directory на портале Назначение или удаление лицензий.

Следующие люди не нуждаются в лицензиях Azure AD Premium Azure AD Basic EDU, которые им назначены:

- Люди, которые являются Microsoft 365 группами и не имеют возможности создавать другие группы.

## <a name="step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups"></a>Шаг 1. Создание группы для пользователей, которым необходимо создать Microsoft 365 групп

Только одна группа в вашей организации может использоваться для управления тем, кто может создавать группы. Но вы можете вложенные другие группы в качестве членов этой группы.

Администраторы в перечисленных выше ролях не должны быть членами этой группы: они сохраняют возможность создавать группы.

1. В центре администрирования перейдите на страницу [Группы](https://admin.microsoft.com/adminportal/home#/groups).

2. Нажмите **кнопку Добавить группу**.

3. Выберите нужный тип группы. Запомните имя группы. Он потребуется позже.

4. Завершите настройку группы, добавив людей или другие группы, которые вы хотите иметь возможность создавать группы в вашей организации.

Подробные инструкции см. в [публикации Create, edit или delete a security group in the Microsoft 365 admin center.](../admin/email/create-edit-or-delete-a-security-group.md)

## <a name="step-2-run-powershell-commands"></a>Шаг 2. Запуск команд PowerShell

Необходимо использовать предварительную версию [Azure Active Directory PowerShell для Graph AzureAD (имя](/powershell/azure/active-directory/install-adv2) модуля **AzureADPreview),** чтобы изменить параметр гостевого доступа на уровне группы:

- Если вы еще не установили ни одной версии модуля Azure AD PowerShell, см. раздел [Установка модуля Azure AD](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview) и следуйте инструкциям по установке общедоступной предварительной версии.

- Если у вас установлена общедоступная версия 2.0 модуля Azure AD PowerShell (AzureAD), вам требуется удалить ее, выполнив команду `Uninstall-Module AzureAD` в сеансе PowerShell, а затем установить предварительную версию, выполнив команду `Install-Module AzureADPreview`.

- Если вы уже установили предварительную версию, выполните команду `Install-Module AzureADPreview`, чтобы убедиться, что это последняя версия модуля.

Скопируйте сценарий ниже в текстовый редактор, например Блокнот или [Windows PowerShell ISE.](/powershell/scripting/components/ise/introducing-the-windows-powershell-ise)

Замените *\<GroupName\>* имя созданной группы. Пример.

`$GroupName = "Group Creators"`

Сохраните файл как GroupCreators.ps1.

В окне PowerShell перейдите к расположению, в котором сохранен файл (тип <FileLocation> "CD").

Запустите сценарий, введя:

`.\GroupCreators.ps1`

и [во входе в учетную запись администратора](../enterprise/connect-to-microsoft-365-powershell.md#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) при запросе.

```PowerShell
$GroupName = "<GroupName>"
$AllowGroupCreation = $False

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

Последняя строка скрипта отображает обновленные параметры:

![Снимок экрана вывода скрипта PowerShell.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

Если в будущем необходимо изменить используемую группу, можно перезахоранить сценарий с именем новой группы.

Если вы хотите отключить ограничение создания группы и снова разрешить всем пользователям создавать группы, установите $GroupName "" и $AllowGroupCreation "True" и перезапустите сценарий.

## <a name="step-3-verify-that-it-works"></a>Шаг 3. Проверка

Для внесения изменений может занять 30 минут или более. Вы можете проверить новые параметры, делая следующие:

1. Вопишите Microsoft 365 с учетной записью пользователя, у которого не должно быть возможности создавать группы. То есть они не являются членом созданной группы или администратором.

2. Выберите **плитку Planner.**

3. В Планировщике выберите **Новый план** в левой навигации, чтобы создать план.

4. Вы должны получить сообщение о том, что планирование и создание группы отключены.

Попробуйте повторить ту же процедуру с участником группы.

> [!NOTE]
> Если члены группы не могут создавать группы, убедитесь, что они не заблокированы с помощью политики [почтовых ящиков OWA.](/powershell/module/exchange/set-owamailboxpolicy)

## <a name="related-topics"></a>Связанные статьи

[Пошаговая пошаговая работа по планированию управления совместной работой](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Создание плана управления совместной работой](collaboration-governance-first.md)

[Начало работы с Office 365 PowerShell](../enterprise/getting-started-with-microsoft-365-powershell.md)

[Настройка управления группой самообслуживки в Azure Active Directory](/azure/active-directory/users-groups-roles/groups-self-service-management)

[Set-ExecutionPolicy](/powershell/module/microsoft.powershell.security/set-executionpolicy).

[Командлеты Azure Active Directory для настройки параметров группы](/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
