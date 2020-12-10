---
title: Предоставление пользователям доступа к Центру безопасности и соответствия требованиям
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.PermissionsHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: Пользователям необходимо назначить разрешения в центре безопасности & Microsoft 365, чтобы они могли управлять любыми функциями обеспечения безопасности или соответствия требованиям.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1bf8da85a0e090a9d74934ea5084f547d6a8794f
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616612"
---
# <a name="give-users-access-to-the-security--compliance-center"></a>Предоставление пользователям доступа к Центру безопасности и соответствия требованиям

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Пользователям необходимо назначить разрешения в центре безопасности & соответствия требованиям, прежде чем они смогут управлять любыми функциями обеспечения безопасности или соответствия требованиям. В качестве глобального администратора или члена группы ролей Организатионманажемент в центре безопасности & соответствия требованиям вы можете предоставить эти разрешения пользователям. Пользователи смогут управлять только теми функциями безопасности и соответствия требованиям, к которым вы предоставите им доступ.

Для получения дополнительных сведений о различных разрешениях, которые вы можете предоставить пользователям в центре безопасности & соответствия требованиям, изучите [разрешения в центре безопасности & соответствия требованиям](permissions-in-the-security-and-compliance-center.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Чтобы выполнить действия, описанные в этой статье, необходимо быть глобальным администратором или членом группы ролей Организатионманажемент в центре безопасности & соответствия требованиям.

- Группы ролей для центра безопасности & соответствия требованиям могут иметь похожие имена для групп ролей в Exchange Online, но они не совпадают.

- Сведения о членстве в группах ролей не являются общими для Exchange Online и центра безопасности & соответствия требованиям.

- Права на делегированный доступ (с правами администратора) с правами администратора от имени (АОБО) не могут получить доступ к центру безопасности & соответствия требованиям.

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a>Использование центра безопасности & соответствия требованиям для предоставления другому пользователю доступа к центру безопасности & соответствия требованиям

1. Откройте центр безопасности & соответствия требованиям <https://protection.office.com> и перейдите к разделу **разрешения**. Чтобы перейти непосредственно на вкладку **разрешения** , откройте <https://protection.office.com/permissions> .

2. В списке групп ролей выберите группу ролей, а затем щелкните **изменить** ![ значок редактирования ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) .

3. На странице свойств группы ролей в разделе **Участники** нажмите **Добавить** ![ значок Добавить ](../../media/ITPro-EAC-AddIcon.gif) и выберите имя пользователя (или пользователей), которого вы хотите добавить.

4. Выбрав всех пользователей, которых вы хотите добавить в группу ролей, нажмите кнопку **Add (добавить \> )** , а затем кнопку **ОК**.

5. Выполнив необходимые действия, нажмите кнопку **Сохранить**.

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>Используйте PowerShell центра безопасности & соответствия требованиям, чтобы предоставить другому пользователю доступ к центру безопасности & соответствия требованиям

1. [Подключитесь к Центру безопасности и соответствия требованиям PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).

2. Используйте указанный ниже синтаксис.

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

Подробные сведения о синтаксисе и параметрах можно найти в статье [Add/RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)

### <a name="how-do-you-know-this-worked"></a>Как убедиться, что все получилось?

Чтобы убедиться, что вы успешно предоставили доступ к центру безопасности & соответствия требованиям, выполните одно из указанных ниже действий.

- В центре безопасности & соответствия требованиям перейдите к разделу **разрешения** и выберите группу ролей. В открывшемся всплывающем окне сведения проверьте членов группы ролей.

- В PowerShell центра безопасности & соответствия требованиям замените \<RoleGroupName\> имя группы ролей и выполните следующую команду:

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).
