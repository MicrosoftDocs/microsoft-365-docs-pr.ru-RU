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
description: Администраторы могут узнать, как назначать или удалять разрешения в центре администрирования Exchange (EAC) в Exchange Online Protection.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5e712c47d49508934ec7dd2438beff00eb6e1a20
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926884"
---
# <a name="manage-role-groups-in-standalone-eop"></a>Управление ролевыми группами в автономной службе EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
-  [Автономный exchange Online Protection](exchange-online-protection-overview.md)

В автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online можно использовать центр администрирования Exchange (EAC) для добавления пользователей в группы ролей. Добавление пользователей в группу ролей дает пользователям разрешения на выполнение определенных задач администрирования. Вы также можете удалить пользователей из групп ролей.

Дополнительные сведения о ролях и группах ролей см. в рублях [Permissions in standalone EOP.](feature-permissions-in-eop.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Чтобы открыть центр администрирования Exchange (EAC), см. в центре администрирования Exchange в режиме [автономный EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Чтобы открыть автономный EOP PowerShell, см. в обзоре [Connect to Exchange Online Protection PowerShell.](/powershell/exchange/connect-to-exchange-online-protection-powershell)

- Вам необходимо получить разрешения в Exchange Online Protection, прежде чем вы сможете сделать процедуры в этой статье. В частности, вам нужна роль **"Управление** ролью", которая по умолчанию назначена группе ролей **"Управление** организацией". Дополнительные сведения см. в рублях Разрешения в автономных [EOP](feature-permissions-in-eop.md) и Use the EAC изменить список участников [в группах ролей.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Сведения о ярлыках клавиатуры, которые могут применяться к процедурам в этой статье, см. в статье Клавишные ярлыки для центра администрирования Exchange в [Exchange Online.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> Возникли проблемы? Обратитесь за помощью на форум по [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE).

## <a name="use-the-eac-to-manage-role-groups"></a>Использование EAC для управления группами ролей

### <a name="use-the-eac-to-view-role-groups"></a>Использование EAC для просмотра групп ролей

1. В EAC перейдите к **роли Администратора** \> **разрешений**. Здесь перечислены все группы ролей в организации.

2. Выберите группу ролей. На области Details показаны **имя,** **описание,** **назначены роли** и **управляемые** группой ролей. Вы также можете увидеть эту информацию, щелкнув **значок Edit** ![ Edit ](../../media/ITPro-EAC-EditIcon.png) .

### <a name="use-the-eac-to-create-role-groups"></a>Использование EAC для создания групп ролей

При создании новой группы ролей можно настроить все параметры самостоятельно (при создании группы или после). Или можно скопировать существующую группу ролей и изменить ее.

1. В EAC перейдите к роли **администратора permissions** и сделайте \> один из следующих действий:

   - **Вручную создайте новую группу ролей:** нажмите **кнопку Добавить значок** ![ Добавить ](../../media/ITPro-EAC-AddIcon.png) .

   - **Скопируйте существующую группу** ролей: выберите группу ролей, которую необходимо скопировать, а затем нажмите **значок Copy** ![ Copy ](../../media/ITPro-EAC-CopyIcon.png) .

2. В **окне "Новая группа** ролей", которое отображается, настройте следующие параметры:

    - **Имя.** Введите уникальное имя для группы ролей.

    - **Описание.** Введите необязательное описание группы ролей.

    - **Роли.** **Нажмите кнопку Добавить** значок Добавить или Удалить значок Удалить, чтобы выбрать или изменить роли, которые назначены ![ группе ](../../media/ITPro-EAC-AddIcon.png)  ![ ](../../media/ITPro-EAC-RemoveIcon.gif) ролей.

    - **Участники.** **Нажмите кнопку Добавить** ![ значок Добавить или ](../../media/ITPro-EAC-AddIcon.png) **Удалить** ![ значок ](../../media/ITPro-EAC-RemoveIcon.gif) Удалить, чтобы изменить членство в группе ролей.

3. По завершению щелкните **Сохранить,** чтобы создать группу ролей.

### <a name="use-the-eac-to-modify-role-groups"></a>Использование EAC для изменения групп ролей

В EAC перейдите к роли **Администратора разрешений,** выберите группу ролей, которую необходимо изменить, а затем нажмите \>  **кнопку Изменить** ![ изменить ](../../media/ITPro-EAC-EditIcon.png) значок .

При изменении групп ролей доступны те же параметры, что и при создании групп ролей. Вы можете выполнить указанные ниже действия.

- Измените имя и описание.

- Добавление и удаление ролей управления (создание или удаление назначений ролей).

- Добавление и удаление участников.

**Примечание.** Некоторые группы ролей (например, Управление организацией) ограничивают роли, которые можно удалить из группы.

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a>Использование EAC измените список участников в группах ролей

1. В EAC перейдите к роли **Администратора** разрешений, выберите группу ролей, которую необходимо изменить, а затем нажмите \>  **кнопку Изменить** ![ значок Редактирование ](../../media/ITPro-EAC-EditIcon.png) .

2. На странице свойства групп ролей, открываемой в разделе **Members,** сделайте один из следующих действий:

   - Нажмите **кнопку Добавить** ![ значок Добавить ](../../media/ITPro-EAC-AddIcon.png) . На странице, которая появится, найдите пользователя, который wou хотите добавить, а затем нажмите **кнопку добавить ->**. Выберите пользователей и **нажмите кнопку добавить ->** раз по мере необходимости. После этого нажмите кнопку **ОК**.

   - Выберите пользователей, которые необходимо удалить, а затем нажмите **кнопку Удалить значок Удалить** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .

3. По завершении нажмите кнопку **Сохранить**.

   > [!NOTE]
   > После добавления или удаления членов группы ролей данным пользователям необходимо выйти из системы, а затем снова войти в нее, чтобы изменить административные права.

### <a name="use-the-eac-to-remove-role-groups"></a>Использование EAC для удаления групп ролей

Вы не можете удалить встроенные группы ролей, но вы можете удалить созданные настраиваемые группы ролей.

1. В EAC перейдите к **роли Администратора** \> **разрешений**.

2. Выберите группу ролей, которую необходимо удалить, а затем нажмите **кнопку Удалить значок Удалить** ![ ](../../media/ITPro-EAC-DeleteIcon.png) .

3. Нажмите **кнопку Да** в появится окно подтверждения.

## <a name="use-powershell-to-manage-role-groups"></a>Использование PowerShell для управления группами ролей

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a>Использование автономных групп ролей EOP PowerShell

Чтобы просмотреть группу ролей, используйте следующий синтаксис:

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

В этом примере возвращается сводный список всех групп ролей.

```PowerShell
Get-RoleGroup
```

В этом примере возвращаются подробные сведения для группы ролей с именем Администраторы получателей.

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

В этом примере возвращаются все группы ролей, в которых пользователь Юлия является участником. Для Юлии необходимо использовать значение DistinguishedName (DN), которое можно найти при запуске команды: `Get-User -Identity Julia | Format-List DistinguishedName` .

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

Дополнительные сведения о синтаксисе и параметрах см. в разделе [Get-RoleGroup](/powershell/module/exchange/Get-RoleGroup).

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a>Использование автономных групп EOP PowerShell для создания групп ролей

При создании новой группы ролей можно настроить все параметры вручную (при создании группы или после). Или можно скопировать существующую группу ролей и изменить ее.

- Чтобы вручную создать новую группу ролей, используйте следующий синтаксис:

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - Параметр _Roles_ указывает роли управления для назначения группе ролей с помощью следующего синтаксиса. `"Role1","Role1",..."RoleN"` Доступные роли можно увидеть с помощью команды **Get-ManagementRole.**

  - Параметр _Members_ указывает членов группы ролей с помощью следующего синтаксиса: `"Member1","Member2",..."MemberN"` . Можно указать пользователей, универсальные группы безопасности с поддержкой почты (USGs) или другие группы ролей (принципы безопасности).

  В этом примере создается новая группа ролей с именем "Управление ограниченными получателями" со следующими настройками:

  - Роль получателей почты назначена группе ролей.

  - Пользователи Ким и Мартин добавляются в качестве участников.

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- Чтобы скопировать существующую группу ролей, сделайте следующие действия:

  1. Сохраните группу ролей, которую необходимо копировать, в переменной с помощью следующей синтаксической конструкции:

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. Создайте новую группу ролей с помощью следующего синтаксиса:

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     Параметр _Members_ указывает членов группы ролей с помощью следующего синтаксиса: `"Member1","Member2",..."MemberN"` . Можно указать пользователей, универсальные группы безопасности с поддержкой почты (USGs) или другие группы ролей (принципы безопасности).

     В этом примере группа ролей управления организацией копируется в новую группу ролей с именем "Управление ограниченной организацией". Участниками группы ролей являются Изабель, Картер и Лукас.

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

Подробные сведения о синтаксисах и параметрах можно получить [в New-RoleGroup.](/powershell/module/exchange/New-RoleGroup)

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a>Использование автономных EOP PowerShell измените список участников в группах ролей

- Команды **Add-RoleGroupMember** и **Remove-RoleGroupMember** добавляют или удаляют отдельных участников по одному. Комлет **Update-RoleGroupMember** может заменить или изменить существующий список участников.

- Членами группы ролей могут быть пользователи, универсальные группы безопасности с поддержкой почты (USGs) или другие группы ролей (принципы безопасности).

Чтобы изменить членов группы ролей, используйте следующий синтаксис:

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- Чтобы _заменить_ существующий список участников значениями, которые вы указываете, используйте следующий синтаксис: `"Member1","Member2",..."MemberN"` .

- Чтобы _выборочно_ изменить существующий список участников, используйте следующий синтаксис: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` .

В этом примере все текущие члены группы ролей службы поддержки заменяются указанными пользователями.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

В этом примере Daigoro Akai удаляет Валерию Баррио из списка участников группы ролей службы поддержки.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

Подробные сведения о синтаксисах и параметрах см. в [обзоре Update-RoleGroupMember.](/powershell/module/exchange/Update-RoleGroupMember)

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a>Для удаления групп ролей используйте автономные группы EOP PowerShell

Вы не можете удалить встроенные группы ролей, но вы можете удалить созданные настраиваемые группы ролей.

Чтобы удалить настраиваемую группу ролей, используйте следующий синтаксис:

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

В этом примере удаляется группа ролей "Обучающие администраторы".

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

Дополнительные сведения о синтаксисе и параметрах см. в разделе [Remove-RoleGroup](/powershell/module/exchange/Remove-RoleGroup).

### <a name="how-do-you-know-these-procedures-worked"></a>Как проверить, что эти процедуры выполнены?

Чтобы убедиться, что вы успешно скопировали группу ролей, сделайте один из следующих действий:

- В EAC перейдите к роли **Администратор разрешений** и убедитесь, что указана (или не указана) группа \> ролей. Выберите группу ролей и проверьте параметры в области Details или щелкните **значок Edit** ![ Edit для ](../../media/ITPro-EAC-EditIcon.png) проверки параметров.

- В Exchange Online PowerShell замените имя группы ролей и запустите следующую команду для проверки существования группы ролей (или ее не существует) и проверки \<Role Group Name\> параметров:

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```