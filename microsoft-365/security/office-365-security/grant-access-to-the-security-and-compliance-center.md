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
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: Пользователям необходимо получить разрешения в центре Microsoft 365 безопасности &, прежде чем они смогут управлять любыми его функциями безопасности или соответствия требованиям.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7cd36ac0dec20851a423acd58e5ad7d38cb65d93
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599927"
---
# <a name="give-users-access-to-the-security--compliance-center"></a>Предоставление пользователям доступа к Центру безопасности и соответствия требованиям

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Пользователям необходимо получить разрешения в Центре & безопасности, прежде чем они смогут управлять любыми его функциями безопасности или соответствия требованиям. Как глобальный администратор или член группы ролей OrganizationManagement в Центре & соответствия требованиям, вы можете предоставить эти разрешения пользователям. Пользователи смогут управлять только теми функциями безопасности и соответствия требованиям, к которым вы предоставите им доступ.

Дополнительные сведения о различных разрешениях, которые можно предоставить пользователям в Центре & безопасности, ознакомьтесь с разрешениями в Центре & [безопасности.](permissions-in-the-security-and-compliance-center.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Чтобы завершить действия в этой статье, необходимо быть глобальным администратором или членом группы ролей OrganizationManagement в Центре & безопасности.

- Группы ролей для Центра & безопасности могут иметь похожие имена с группами ролей в Exchange Online, но они не одинаковы.

- Членство в группах ролей не разделяется между Exchange Online и Центром & безопасности.

- Партнеры по делегированию разрешений доступа (DAP) с разрешениями администрирования от имени (AOBO) не могут получить доступ к Центру & безопасности.

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a>Используйте Центр & безопасности, чтобы предоставить другому пользователю доступ к Центру & соответствия требованиям.

1. Откройте центр & безопасности и <https://protection.office.com> перейдите к **разрешениям.** Чтобы перейти непосредственно на **вкладку Permissions,** откройте <https://protection.office.com/permissions> .

2. Из списка групп ролей выберите группу ролей и нажмите кнопку **Изменить значок Изменить** ![ ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) .

3. На странице свойства группы ролей в статье **Участники** нажмите кнопку **Добавить** значок добавить и выберите имя пользователя ![ (или пользователей), которое вы хотите ](../../media/ITPro-EAC-AddIcon.gif) добавить.

4. Когда вы выбрали всех пользователей, которые необходимо добавить в группу ролей, нажмите **кнопку добавить \> и** затем **ОК**.

5. Выполнив необходимые действия, нажмите кнопку **Сохранить**.

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>Используйте центр & безопасности PowerShell, чтобы предоставить другому пользователю доступ к Центру & безопасности

1. [Подключение к Центру безопасности и соответствия требованиям Windows PowerShell](/powershell/exchange/connect-to-scc-powershell).

2. Используйте следующий синтаксис:

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

Подробные вопросы синтаксиса и параметров см. в [добавлении-RoleGroupMember](/powershell/module/exchange/add-rolegroupmember)

### <a name="how-do-you-know-this-worked"></a>Как убедиться, что все получилось?

Чтобы убедиться, что вы успешно предоставили доступ к Центру & безопасности, сделайте один из следующих действий:

- В Центре & безопасности перейдите в **Центр разрешений** и выберите группу ролей. В открываемом флаауте подробно проверьте членов группы ролей.

- В центре & безопасности PowerShell замените имя группы ролей и запустите \<RoleGroupName\> следующую команду:

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  Подробные сведения о синтаксисах и параметрах см. в [обзоре Get-RoleGroupMember.](/powershell/module/exchange/Get-RoleGroupMember)