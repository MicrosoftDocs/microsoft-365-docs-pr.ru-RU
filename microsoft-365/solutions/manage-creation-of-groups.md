---
title: Управление тем, кто может создавать группы Microsoft 365
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
description: Узнайте, как управлять тем, какие пользователи могут создавать группы Microsoft 365.
ms.openlocfilehash: 3fa430e44c272e5ababbfb0e4befba707c72c1ba
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122388"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a>Управление тем, кто может создавать группы Microsoft 365

По умолчанию все пользователи могут создавать группы Microsoft 365. Это рекомендуемый подход, так как он позволяет пользователям начать совместную работу без помощи ИТ-сотрудников.

Если в вашей организации требуется ограничить пользователей, которые могут создавать группы, это можно сделать, вы следуя процедурам, которые данной статьи. Когда вы ограничиваете пользователей, которые могут создавать группы, это влияет на все службы, которые используют группы для доступа, в том числе:

- Outlook
- SharePoint
- Yammer
- Microsoft Teams
- Microsoft Stream
- Планировщик
- Power BI (классическая)
- Проект в Интернете / План

Создание группы Microsoft 365 можно ограничить только членами определенной группы Microsoft 365 или группы безопасности. Чтобы настроить его, используйте Windows PowerShell. В этой статье данная статья посвящена всем необходимым этапам.

Действия, которые необходимо предпринять в этой статье, не препятствуют созданию групп участниками определенных ролей. Глобальные администраторы Office 365 могут создавать группы любыми способами, такими как Центр администрирования Microsoft 365, Планировщик, Teams, Exchange и SharePoint Online. Другие роли могут создавать группы с помощью ограниченных средств, перечисленных ниже.

- Администратор Exchange: Центр администрирования Exchange, Azure AD
- Поддержка уровня 1 для партнеров: Центр администрирования Microsoft 365, Центр администрирования Exchange, Azure AD
- Поддержка уровня 2 для партнеров: Центр администрирования Microsoft 365, Центр администрирования Exchange, Azure AD
- Авторы каталогов: Azure AD
- Администратор SharePoint: Центр администрирования SharePoint, Azure AD
- Администратор служб Teams: Центр администрирования Teams, Azure AD
- Администратор управления пользователями: Центр администрирования Microsoft 365, Yammer, Azure AD

Если вы входите в одну из этих ролей, вы можете создать группы Microsoft 365 для пользователей с ограниченным доступом, а затем назначить пользователя владельцем группы.

## <a name="licensing-requirements"></a>Требования к лицензированию

Чтобы управлять созданием групп, следующие люди нуждаются в лицензиях Azure AD Premium или назначенной им лицензиях azure AD Basic EDU:

- Администратор, который настраивает эти параметры создания группы
- Члены группы, которым разрешено создавать группы

> [!NOTE]
> Дополнительные сведения о назначении лицензий Azure см. на портале [Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups)

Следующие люди не нуждаются в лицензиях Azure AD Premium или Azure AD Basic EDU, которые им назначены:

- Пользователи, которые являются членами групп Microsoft 365 и не могут создавать другие группы.

## <a name="step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups"></a>Шаг 1. Создание группы для пользователей, которым необходимо создать группы Microsoft 365

Для управления тем, кто может создавать группы, можно использовать только одну группу в организации. Но вы можете вложенные другие группы в качестве членов этой группы.

Администраторы в перечисленных выше ролях не должны быть членами этой группы: они сохраняют возможность создавать группы.

1. В Центре администрирования перейдите на [страницу "Группы".](https://admin.microsoft.com/adminportal/home#/groups)

2. Нажмите **кнопку "Добавить группу".**

3. Выберите нужный тип группы. Запомните имя группы. Он потребуется позже.

4. Завершите настройку группы, добавив пользователей или другие группы, которым вы хотите иметь возможность создавать группы в вашей организации.

Подробные инструкции см. в описании создания, изменения или удаления группы безопасности в Центре администрирования [Microsoft 365.](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group)

## <a name="step-2-run-powershell-commands"></a>Шаг 2. Запуск команд PowerShell

Чтобы изменить параметр гостевого доступа на уровне группы, необходимо использовать предварительную версию [Azure Active Directory PowerShell для Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (имя модуля **AzureADPreview):**

- Если вы еще не установили ни одной версии модуля Azure AD PowerShell, см. раздел [Установка модуля Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) и следуйте инструкциям по установке общедоступной предварительной версии.

- Если у вас установлена общедоступная версия 2.0 модуля Azure AD PowerShell (AzureAD), вам требуется удалить ее, выполнив команду `Uninstall-Module AzureAD` в сеансе PowerShell, а затем установить предварительную версию, выполнив команду `Install-Module AzureADPreview`.

- Если вы уже установили предварительную версию, выполните команду `Install-Module AzureADPreview`, чтобы убедиться, что это последняя версия модуля.

Скопируйте сценарий ниже в текстовый редактор, например Блокнот или [Windows PowerShell ISE.](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise)

Замените *\<GroupName\>* имя созданной группы. Пример:

`$GroupName = "Group Creators"`

Сохраните файл как GroupCreators.ps1.

В окне PowerShell перейдите к расположению, в котором сохранен файл (введите <FileLocation> "CD").

Запустите сценарий, введя:

`.\GroupCreators.ps1`

и [во входе с помощью учетной записи администратора](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) при запросе.

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

В последней строке сценария отобразятся обновленные параметры:

![This is what your settings will look like when you're done.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

Если в будущем вы захотите изменить используемую группу, можно повторно использовать сценарий с именем новой группы.

Если вы хотите отключить ограничение на создание группы и снова разрешить всем пользователям создавать группы, установите для $GroupName "" $AllowGroupCreation "True" и повторно перезапустите сценарий.

## <a name="step-3-verify-that-it-works"></a>Шаг 3. Проверка

Чтобы изменения вступили в силу, может занять 30 минут или больше. Чтобы проверить новые параметры, с помощью следующих параметров:

1. Во sign in to Microsoft 365 with a user account of someone who should NOT have the ability to create groups. То есть они не являются членами группы, которую вы создали, или администратором.

2. Выберите **плитку Планировщика.**

3. В Планировщике выберите **"Новый план"** в области навигации слева, чтобы создать план.

4. Должно отключать планирование и создание групп.

Попробуйте эту же процедуру еще раз с участником группы.

> [!NOTE]
> Если члены группы не могут создавать группы, убедитесь, что они не заблокированы с помощью политики почтовых ящиков [OWA.](https://go.microsoft.com/fwlink/?linkid=852135)

## <a name="related-topics"></a>Связанные статьи

[Пошаговая пошаговая работа по планированию управления совместной работой](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Создание плана управления совместной работой](collaboration-governance-first.md)

[Начало работы с Office 365 PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[Настройка управления самостоятельной группой в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[Set-ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy).

[Командлеты Azure Active Directory для настройки параметров группы](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
