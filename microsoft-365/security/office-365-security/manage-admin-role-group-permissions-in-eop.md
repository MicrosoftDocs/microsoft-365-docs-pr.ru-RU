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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: Администраторы могут научиться назначать и удалять разрешения в Центре администрирования Exchange в Exchange Online Protection.
ms.openlocfilehash: 8d452eb85d59bbe82cc6685d652617bc857c1ddf
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825693"
---
# <a name="manage-role-groups-in-standalone-eop"></a>Управление ролевыми группами в автономном EOP

Для добавления пользователей в группы ролей в автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online можно использовать Центр администрирования Exchange (EAC). Добавление пользователей в группу ролей предоставляет пользователям разрешения на выполнения определенных задач администрирования. Кроме того, можно удалять пользователей из группролей.

Дополнительные сведения о ролях и группах ролей см. в статье ["Разрешения в автономной службе EOP".](feature-permissions-in-eop.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Чтобы открыть Центр администрирования Exchange ,см. раздел [Центра администрирования Exchange в автономной службе EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Чтобы открыть автономную оболочку EOP PowerShell, см. [статью "Подключение к PowerShell для Exchange Online Protection".](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)

- Чтобы вы могли выполнить эти процедуры, вам должны быть назначены соответствующие разрешения. В частности, вам потребуется роль управления ролями, которая по умолчанию назначается группе ролей OrganizationManagement (глобальные администраторы). Дополнительные сведения см. в разделе ["Разрешения в автономной службе EOP"](feature-permissions-in-eop.md) и использовании Центра администрирования [Exchange для изменения списка членов в группах ролей.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Сочетания клавиш для процедур, описанных в этой статье, приведены в разделе сочетания клавиш для [Центра администрирования Exchange в Exchange Online.](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> Возникли проблемы? Обратитесь за помощью на форум по [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).

## <a name="use-the-eac-to-manage-role-groups"></a>Использование Центра администрирования Exchange для управления группами ролей

### <a name="use-the-eac-to-view-role-groups"></a>Использование Центра администрирования Exchange для просмотра групп ролей

1. В Центре администрирования Exchange перейдите к **ролям** \> **администраторов.** Здесь перечислены все группы ролей в организации.

2. Выберите группу ролей. В области сведений **отображаются имя,** **описание,** **назначенные роли** **и управляется** группой ролей. Эти сведения также можно просмотреть, нажав **значок** ![ правки. ](../../media/ITPro-EAC-EditIcon.png)

### <a name="use-the-eac-to-create-role-groups"></a>Использование Центра администрирования Exchange для создания групп ролей

При создании новой группы ролей можно настроить все параметры самостоятельно (во время создания группы или после нее). Или можно скопировать существующую группу ролей и изменить ее.

1. В Центре администрирования Exchange выберите **Permissions** \> **"Роли администраторов"** и выполните одно из следующих действий:

   - **Создайте новую группу ролей вручную:** нажмите **кнопку Добавить** ![ значок "Добавить". ](../../media/ITPro-EAC-AddIcon.png)

   - **Скопируйте существующую группу ролей:** выберите группу ролей, которую необходимо скопировать, и нажмите **значок копирования** ![ ](../../media/ITPro-EAC-CopyIcon.png) копии.

2. В **открывшемся окне** создания группы ролей настройте следующие параметры:

    - **Имя:** введите уникальное имя группы ролей.

    - **Описание:** введите необязательное описание для группы ролей.

    - **Роли:** нажмите **кнопку** ![ "Добавить ](../../media/ITPro-EAC-AddIcon.png) значок **Remove** ![ ](../../media/ITPro-EAC-RemoveIcon.gif)ITPro-EAC-RemoveIcon.gif" для выбора или изменения ролей, назначенных для группы ролей.

    - **Members:** Click **Add** ![ icon or ](../../media/ITPro-EAC-AddIcon.png) **Remove**ITPro-EAC-RemoveIcon.gifto modify the role ![ group ](../../media/ITPro-EAC-RemoveIcon.gif) membership.

3. По завершении нажмите кнопку **"Сохранить",** чтобы создать группу ролей.

### <a name="use-the-eac-to-modify-role-groups"></a>Использование Центра администрирования Exchange для изменения групп ролей

В Центре администрирования Exchange перейдите к **ролям** \> **администраторов,** выберите группу ролей, которую необходимо изменить, и нажмите **значок** ![ ](../../media/ITPro-EAC-EditIcon.png) редактирования.

При изменении групп ролей доступны те же параметры, что и при создании групп ролей. Вы можете выполнить указанные ниже действия.

- Изменить имя и описание.

- Добавление и удаление ролей управления (создания или удаления назначений ролей).

- Добавить и удалить участников.

**Примечание.** Некоторые группы ролей (например, Управление организацией) ограничивают роли, которые можно удалить из группы.

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a>Использование Центра администрирования Exchange для изменения списка членов в группах ролей

1. В Центре администрирования Exchange перейдите к **ролям** администраторов, выберите группу \> **Admin roles**ролей, которую необходимо изменить, и нажмите **значок** ![ ](../../media/ITPro-EAC-EditIcon.png) редактирования.

2. На открывшейся странице свойств группы ролей в разделе **"Участники"** выполните одно из следующих действий:

   - Нажмите **кнопку Add** ![ Icon (Добавить значок. ](../../media/ITPro-EAC-AddIcon.png) На появляющемся странице найдите нужного пользователя и нажмите **кнопку ">. ** Выберите пользователей и **нажмите кнопку ">** добавлять несколько раз при необходимости. После этого нажмите кнопку **ОК**.

   - Выберите пользователей, которых нужно удалить, и нажмите значок **Remove** ![ "Удалить". ](../../media/ITPro-EAC-RemoveIcon.gif)

3. Выполнив необходимые действия, нажмите кнопку **Сохранить**.

   > [!NOTE]
   > После добавления или удаления членов группы ролей данным пользователям необходимо выйти из системы, а затем снова войти в нее, чтобы изменить административные права.

### <a name="use-the-eac-to-remove-role-groups"></a>Использование Центра администрирования Exchange для удаления групп ролей

Встроенные группы ролей удалить невозможно, однако можно удалить созданные пользователем настраиваемые группы ролей.

1. В Центре администрирования Exchange перейдите к **ролям** \> **администраторов.**

2. Выберите группу ролей, которую необходимо удалить, и нажмите **значок "Удалить** ![ удалить". ](../../media/ITPro-EAC-DeleteIcon.png)

3. Нажмите **кнопку "Да"** в открывшемся окне подтверждения.

## <a name="use-powershell-to-manage-role-groups"></a>Использование PowerShell для управления группами ролей

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a>Просмотр групп ролей с помощью автономной службы EOP PowerShell

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

В этом примере возвращаются все группы ролей, в которых является пользователь Julia. Нужно использовать значение DistinguishedName (DN) для Юлиии, которое можно найти, выполнив следующую `Get-User -Identity Julia | Format-List DistinguishedName` команду: .

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

Дополнительные сведения о синтаксисе и параметрах см. в разделе [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a>Создание групп ролей с помощью автономной службы EOP PowerShell

При создании новой группы ролей можно настроить все параметры вручную (при создании группы или после нее). Или можно скопировать существующую группу ролей и изменить ее.

- Чтобы создать новую группу ролей вручную, используйте следующую синтаксическую конпричину:

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - Параметр _Roles указывает роли_ управления, назначаемые группе ролей, используя следующую синтаксическую константу. `"Role1","Role1",..."RoleN"` Доступные роли можно просмотреть с помощью **командлета Get-ManagementRole.**

  - Параметр _Members_ указывает членов группы ролей, используя следующий `"Member1","Member2",..."MemberN"` синтаксис: Можно указать пользователей, универсальные группы безопасности с включенной поддержкой почты и другие группы ролей (участников безопасности).

  В этом примере создается группа ролей с именем Limited Recipient Management со следующими параметрами:

  - Роль получателей почты назначается группе ролей.

  - Пользователи Kim и Мартина добавляются в качестве членов.

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- Чтобы скопировать существующую группу ролей, выполните следующие действия.

  1. Сохраните группу ролей, которую необходимо копировать, в переменной с помощью следующей синтаксической конструкции:

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. Создайте новую группу ролей с помощью следующей синтаксической кончестки:

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     Параметр _Members_ указывает членов группы ролей, используя следующий `"Member1","Member2",..."MemberN"` синтаксис: Можно указать пользователей, универсальные группы безопасности с включенной поддержкой почты и другие группы ролей (участников безопасности).

     В этом примере группа ролей Organization Management копируется в новую группу ролей с именем "Limited Organization Management". Участники группы ролей являются Еабелы, Карталом и Лукасом.

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

Дополнительные сведения о синтаксисе и [параметрах: New-RoleGroup.](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup)

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a>Использование автономного сервиса EOP PowerShell для изменения списка членов в группах ролей

- Командлеты **Add-RoleGroupMember** и **Remove-RoleGroupMember** добавляют или удаляют отдельных членов по одному. Командлет **Update-RoleGroupMember** может заменить или изменить существующий список членов.

- Участниками группы ролей могут быть пользователи, универсальные группы безопасности с включенной поддержкой почты и другие группы ролей (участники безопасности).

Для изменения членов группы ролей используется следующий синтаксис:

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- Для _замены_ существующего списка членов указанными значениями используется следующий `"Member1","Member2",..."MemberN"` синтаксис:

- Для _выборочного_ изменения существующего списка элементов используется следующий `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` синтаксис:

В этом примере показано, как заменить всех текущих членов группы ролей службы поддержки указанными пользователями.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

В этом примере показано, как добавить Daigoro Akai и удалить Мария Барио из списка членов в группе ролей службы поддержки.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

Дополнительные сведения о синтаксисе и параметрах см. [в разделе Update-RoleGroupMember.](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember)

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a>Удаление групп ролей с помощью автономной службы EOP PowerShell

Встроенные группы ролей удалить невозможно, однако можно удалить созданные пользователем настраиваемые группы ролей.

Для удаления настраиваемой группы ролей используется следующий синтаксис:

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

В этом примере удаляется группа ролей "Обучающие администраторы".

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

Дополнительные сведения о синтаксисе и параметрах см. в разделе [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).

### <a name="how-do-you-know-these-procedures-worked"></a>Как проверить, что эти процедуры выполнены?

Чтобы убедиться, что группа ролей скопирована успешно, выполните одно из следующих действий:

- В Центре администрирования Exchange перейдите к **ролям** \> **администраторов**и убедитесь в наличии группы ролей (или нет в списке). Выберите группу ролей и проверьте параметры в области "Сведения" или нажмите значок **Edit** ![ "Изменить" ](../../media/ITPro-EAC-EditIcon.png) для проверки параметров.

- В Exchange Online PowerShell замените именем группы ролей, а затем выполните следующую команду, чтобы убедиться, что группа ролей \<Role Group Name\> существует (или не существует) и проверьте параметры:

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
