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
description: Пользователям должны быть назначены разрешения в Центре безопасности и & соответствия требованиям Microsoft 365, прежде чем они смогут управлять любыми функциями обеспечения безопасности и соответствия требованиям.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e1a619b184c575e3750b2499adc661627b4d27d6
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289881"
---
# <a name="give-users-access-to-the-security--compliance-center"></a>Предоставление пользователям доступа к Центру безопасности и соответствия требованиям

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Пользователям должны быть назначены разрешения в Центре безопасности & соответствия требованиям, прежде чем они смогут управлять функциями безопасности и соответствия требованиям. Как глобальный администратор или участник группы ролей OrganizationManagement в Центре безопасности & соответствия требованиям, вы можете предоставить эти разрешения пользователям. Пользователи смогут управлять только теми функциями безопасности и соответствия требованиям, к которым вы предоставите им доступ.

Дополнительные сведения о различных разрешениях, которые можно предоставить пользователям в Центре безопасности & соответствия требованиям, можно найти в Центре безопасности [& соответствия требованиям.](permissions-in-the-security-and-compliance-center.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Для выполнения действий, которые необходимо выполнить в этой статье, необходимо быть глобальным администратором или членом группы ролей OrganizationManagement в Центре безопасности & соответствия требованиям.

- Группы ролей для Центра & соответствия требованиям могут иметь похожие имена на группы ролей в Exchange Online, но они не одинаковы.

- Членство в группах ролей не совместно с Exchange Online и Центром безопасности & соответствия требованиям.

- Партнеры службы разрешений делегирования доступа (DAP) с разрешениями администрирования от имени (AOBO) не могут получить доступ к Центру безопасности & соответствия требованиям.

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a>Использование Центра безопасности & соответствия требованиям для того, чтобы предоставить другому пользователю доступ к Центру & соответствия требованиям

1. Откройте Центр безопасности & соответствия требованиям и <https://protection.office.com> перейдите к **центру разрешений.** Чтобы перейти непосредственно на **вкладку "Разрешения",** откройте <https://protection.office.com/permissions> .

2. В списке групп ролей выберите группу ролей  и нажмите значок ![ ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) редактирования.

3. На странице свойств группы ролей в группе "Участники" щелкните значок добавления и выберите имя пользователя ![ (или пользователей), которого вы хотите ](../../media/ITPro-EAC-AddIcon.gif) добавить.

4. Выбрав всех пользователей, которые нужно добавить в группу ролей, нажмите кнопку **"Добавить" \>** и нажмите кнопку **"ОК".**

5. По завершении нажмите кнопку **Сохранить**.

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>Использование PowerShell Центра & безопасности для обеспечения доступа других пользователей к Центру безопасности & соответствия требованиям

1. [Подключение к Центру безопасности и соответствия требованиям Windows PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).

2. Используйте указанный ниже синтаксис.

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

Дополнительные сведения о синтаксисах и параметрах см. в описании [add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)

### <a name="how-do-you-know-this-worked"></a>Как убедиться, что все получилось?

Чтобы убедиться, что вы успешно предоставили доступ к Центру безопасности & соответствия требованиям, сделайте следующее:

- В Центре безопасности & соответствия требованиям перейдите в **"Разрешения"** и выберите группу ролей. В открываемом окле сведений проверьте членов группы ролей.

- В PowerShell центра & безопасности замените имя группы ролей и запустите \<RoleGroupName\> следующую команду:

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  Подробные сведения о синтаксисах и параметрах см. в описании [get-RoleGroupMember.](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember)
