---
title: Управление группами ролей в EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: Администраторы могут узнать, как назначать или удалять разрешения в Центре администрирования Exchange (EAC) в Exchange Online Protection.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b53023521f477b5e864424ec648ccf7e5b749d0c
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166991"
---
# <a name="manage-role-groups-in-standalone-eop"></a>Управление ролевыми группами в автономной службе EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
-  [Автономный режим Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)

В автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online для добавления пользователей в группы ролей можно использовать Центр администрирования Exchange (EAC). Добавление пользователей в группу ролей дает им разрешения на выполнение определенных задач администрирования. Вы также можете удалять пользователей из групп ролей.

Дополнительные сведения о ролях и группах ролей см. в [сведениях о разрешениях в автономных EOP.](feature-permissions-in-eop.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Чтобы открыть Центр администрирования Exchange (EAC), см. центр [администрирования Exchange в режиме автономных EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Чтобы открыть автономный EOP PowerShell, см. веб-сайт [Connect to Exchange Online Protection PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)

- Для работы с процедурами, которые данная статья, вам должны быть назначены разрешения в Exchange Online Protection. В частности, необходима роль **управления** ролем, которая по умолчанию назначена группе ролей **"Управление** организацией". Дополнительные сведения см. в сведениях о разрешениях в автономных [EOP](feature-permissions-in-eop.md) и использовании EAC для изменения списка участников [в группах ролей.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Сведения о сочетаниях клавиш, которые могут применяться к процедурам в этой статье, см. в статье "Сочетания клавиш" в Центре администрирования [Exchange в Exchange Online.](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> Возникли проблемы? Обратитесь за помощью на форум по [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).

## <a name="use-the-eac-to-manage-role-groups"></a>Использование EAC для управления группами ролей

### <a name="use-the-eac-to-view-role-groups"></a>Просмотр групп ролей с помощью EAC

1. В EAC перейдите к **ролям** \> **администратора разрешений.** Здесь перечислены все группы ролей в организации.

2. Выберите группу ролей. В области сведений показаны **имена,** **описание,** назначенная **роль** и управление **группой** ролей. Вы также можете увидеть эти  сведения, щелкнув значок ![ ](../../media/ITPro-EAC-EditIcon.png) редактирования.

### <a name="use-the-eac-to-create-role-groups"></a>Создание групп ролей с помощью EAC

При создании новой группы ролей можно настроить все параметры самостоятельно (во время создания группы или после нее). Кроме того, можно скопировать существующую группу ролей и изменить ее.

1. В EAC перейдите к **ролям** администратора разрешений \> и сделайте одно из следующих действий:

   - **Вручную создайте новую группу ролей:** щелкните **значок** ![ ](../../media/ITPro-EAC-AddIcon.png) "Добавить".

   - **Скопируйте существующую группу** ролей: выберите группу ролей, которую нужно скопировать, и щелкните значок  ![ ](../../media/ITPro-EAC-CopyIcon.png) копирования.

2. В новом **окне** группы ролей настройте следующие параметры:

    - **Name**: Enter a unique name for the role group.

    - **Описание:** введите необязательное описание группы ролей.

    - **Roles**: Click **Add** ![ Add icon or Remove ](../../media/ITPro-EAC-AddIcon.png) **Remove** icon to select or modify the roles that ![ are ](../../media/ITPro-EAC-RemoveIcon.gif) assigned to the role group.

    - **Участники:** **щелкните значок "Добавить** добавить" или ![ ](../../media/ITPro-EAC-AddIcon.png) **"Удалить** ![ значок "Удалить", ](../../media/ITPro-EAC-RemoveIcon.gif) чтобы изменить членство в группе ролей.

3. После завершения нажмите кнопку  "Сохранить", чтобы создать группу ролей.

### <a name="use-the-eac-to-modify-role-groups"></a>Использование EAC для изменения групп ролей

В EAC перейдите к **ролям** администратора разрешений, выберите группу ролей, которую нужно изменить, и нажмите значок \>   ![ ](../../media/ITPro-EAC-EditIcon.png) редактирования.

При изменении групп ролей доступны те же параметры, что и при создании групп ролей. Вы можете выполнить указанные ниже действия.

- Измените имя и описание.

- Добавление и удаление ролей управления (создание или удаление назначений ролей).

- Добавление и удаление участников.

**Примечание.** Некоторые группы ролей (например, Управление организацией) ограничивают роли, которые можно удалить из группы.

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a>Изменение списка участников в группах ролей с помощью EAC

1. В EAC перейдите к **ролям** администратора разрешений, выберите группу ролей, которую нужно изменить, и нажмите значок \>   ![ ](../../media/ITPro-EAC-EditIcon.png) редактирования.

2. На открываемой странице свойств группы ролей в разделе **"Участники"** сделайте один из следующих действий:

   - Нажмите **кнопку "Добавить** ![ значок добавления" ](../../media/ITPro-EAC-AddIcon.png) . На этой странице найдите пользователя, который нужно добавить, и нажмите кнопку **add ->**. Выберите пользователей и **нажмите кнопку add ->** многократно при необходимости. После этого нажмите кнопку **ОК**.

   - Выберите пользователей, которые нужно удалить, и нажмите значок **"Удалить** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) удалить".

3. По завершении нажмите кнопку **Сохранить**.

   > [!NOTE]
   > После добавления или удаления членов группы ролей данным пользователям необходимо выйти из системы, а затем снова войти в нее, чтобы изменить административные права.

### <a name="use-the-eac-to-remove-role-groups"></a>Удаление групп ролей с помощью EAC

Встроенные группы ролей удалить нельзя, но вы можете удалить созданные настраиваемые группы ролей.

1. В EAC перейдите к **ролям** \> **администратора разрешений.**

2. Выберите группу ролей, которую нужно удалить, и нажмите **значок "Удалить** ![ удалить". ](../../media/ITPro-EAC-DeleteIcon.png)

3. Нажмите **кнопку "Да"** в от появится окно подтверждения.

## <a name="use-powershell-to-manage-role-groups"></a>Управление группами ролей с помощью PowerShell

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a>Просмотр групп ролей с помощью автономных EOP PowerShell

Чтобы просмотреть группу ролей, используйте следующий синтаксис:

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

В этом примере возвращается сводный список всех групп ролей.

```PowerShell
Get-RoleGroup
```

В этом примере возвращаются подробные сведения о группе ролей с именем Recipient Administrators.

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

В этом примере возвращаются все группы ролей, участником которых является пользователь Юлия. Необходимо использовать значение DistinguishedName (DN) для Юлии, которое можно найти с помощью команды: `Get-User -Identity Julia | Format-List DistinguishedName` .

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

Дополнительные сведения о синтаксисе и параметрах см. в разделе [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a>Создание групп ролей с помощью автономных EOP PowerShell

При создании новой группы ролей можно настроить все параметры вручную (во время создания группы или после нее). Кроме того, можно скопировать существующую группу ролей и изменить ее.

- Чтобы вручную создать новую группу ролей, используйте следующий синтаксис:

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - Параметр _Roles_ указывает роли управления, назначаемые группе ролей, с помощью следующего синтаксиса. `"Role1","Role1",..."RoleN"` Доступные роли можно увидеть с помощью команды **Get-ManagementRole.**

  - Параметр _Members_ указывает членов группы ролей с помощью следующего синтаксиса: `"Member1","Member2",..."MemberN"` . Можно указать пользователей, универсальные группы безопасности с включенной поддержкой почты или другие группы ролей (участников безопасности).

  В этом примере создается группа ролей с именем "Limited Recipient Management" со следующими настройками:

  - Группе ролей назначена роль получателей почты.

  - Пользователи Kim и Martin добавляются в качестве участников.

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- Чтобы скопировать существующую группу ролей, сделайте следующее:

  1. Сохраните группу ролей, которую необходимо копировать, в переменной с помощью следующей синтаксической конструкции:

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. Создайте новую группу ролей, используя следующий синтаксис:

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     Параметр _Members_ указывает членов группы ролей с помощью следующего синтаксиса: `"Member1","Member2",..."MemberN"` . Можно указать пользователей, универсальные группы безопасности с включенной поддержкой почты или другие группы ролей (участников безопасности).

     В этом примере группа ролей Управление организацией копируется в новую группу ролей с именем "Limited Organization Management". Участниками группы ролей являются Isabelle, Carter и Lukas.

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

Подробные сведения о синтаксисах и параметрах: [New-RoleGroup.](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup)

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a>Использование автономных EOP PowerShell для изменения списка участников в группах ролей

- С **их стороны можно**  добавлять или удалять отдельных участников по одному. Для замены или изменения существующего списка членов можно использовать команды **Update-RoleGroupMember.**

- Участниками группы ролей могут быть пользователи, универсальные группы безопасности с включенной поддержкой почты или другие группы ролей (участники безопасности).

Чтобы изменить членов группы ролей, используйте следующий синтаксис:

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- Чтобы _заменить_ существующий список членов на задамые вами значения, используйте следующий синтаксис: `"Member1","Member2",..."MemberN"` .

- Чтобы _выборочно_ изменить существующий список членов, используйте следующий синтаксис: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` .

В этом примере все текущие члены группы ролей "Help Desk" заменяются указанными пользователями.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

В этом примере daigoro Akai и Valeria Barrio удаляется из списка членов группы ролей "Help Desk".

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

Подробные сведения о синтаксисах и параметрах см. в описании [Update-RoleGroupMember.](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember)

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a>Удаление групп ролей с помощью автономных EOP PowerShell

Встроенные группы ролей удалить нельзя, но вы можете удалить созданные настраиваемые группы ролей.

Чтобы удалить настраиваемую группу ролей, используйте следующий синтаксис:

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

В этом примере удаляется группа ролей "Обучающие администраторы".

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

Дополнительные сведения о синтаксисе и параметрах см. в разделе [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).

### <a name="how-do-you-know-these-procedures-worked"></a>Как проверить, что эти процедуры выполнены?

Чтобы убедиться, что вы успешно скопировали группу ролей, сделайте следующее:

- В EAC перейдите к **ролям** администратора разрешений и убедитесь, что группа ролей указана \> (или не указана). Выберите группу ролей и проверьте параметры в области  сведений или нажмите значок редактирования, чтобы ![ проверить ](../../media/ITPro-EAC-EditIcon.png) параметры.

- В Exchange Online PowerShell замените имя группы ролей и запустите следующую команду, чтобы убедиться, что группа ролей существует (или не существует) и \<Role Group Name\> проверить параметры:

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
