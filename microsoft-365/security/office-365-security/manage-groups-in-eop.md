---
title: Управление группами в EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
description: С помощью Exchange Online Protection (EOP) для организации Exchange можно создавать группы с включенной поддержкой почты. EOP также позволяет определять или обновлять свойства групп, указывающие членство, адреса электронной почты и другие данные групп.
ms.openlocfilehash: ae4e0a8c39c97720cb51c0f5d7b69547258b11b7
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598996"
---
# <a name="manage-groups-in-eop"></a>Управление группами в EOP

 С помощью Exchange Online Protection (EOP) для организации Exchange можно создавать группы с включенной поддержкой почты. EOP также позволяет определять или обновлять свойства групп, указывающие членство, адреса электронной почты и другие данные групп. В зависимости от своих требований вы можете создать группы рассылки или группы безопасности. Такие группы можно создать с помощью Центра администрирования Exchange или удаленной консоли Windows PowerShell.

## <a name="types-of-mail-enabled-groups"></a>Типы групп с включенной поддержкой почты

Для организации Exchange вы можете создать группы двух типов.

- Группы рассылки — это коллекции пользователей электронной почты, таких как группа или другая группа "ad hoc", которая должна получать или отправлять электронную почту относительно общей области. Группы рассылки создаются исключительно для распространения сообщений электронной почты. В EOP под группой рассылки подразумевается любая группа с включенной поддержкой почты вне зависимости от ее контекста безопасности.

- Группы безопасности — это коллекции пользователей электронной почты, которым требуются разрешения на доступ для ролей администратора. Например, вам может понадобиться предоставить определенной группе пользователей разрешения на уровне роли администратора, чтобы они могли настраивать параметры защиты от нежелательной почты и вредоносных программ.

    > [!NOTE]
    > По умолчанию все новые группы безопасности требуют проверки подлинности всех отправителей. Это запрещает внешним отправителям отправлять сообщения в группы безопасности с включенной поддержкой почты.

## <a name="before-you-begin"></a>Приступая к работе

- Для выполнения этих процедур необходимы соответствующие разрешения. Сведения о необходимых разрешениях см. в статье Запись "Группы рассылки и группы безопасности" в разделе [Разрешения на функции в службе EOP](feature-permissions-in-eop.md).

- Чтобы открыть центр администрирования Exchange, ознакомьтесь со статьей [центр администрирования Exchange в Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).

- Имейте в виду, что при создании групп и управлении ими с помощью командлетов PowerShell для Exchange Online Protection вы можете столкнуться с регулированием.

- В процедурах PowerShell, приведенных в этом разделе, используется метод пакетной обработки, который приводит к задержке распространения в течение нескольких минут до того, как результаты команд будут видны.

- Сведения об использовании Windows PowerShell для подключения к службе Exchange Online Protection см. в статье [Подключение к PowerShell для Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Дополнительные сведения о сочетаниях клавиш, которые могут применяться к процедурам, описанным в этой статье, приведены в статье [сочетания клавиш для центра администрирования Exchange в Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Возникли проблемы? Обратитесь за помощью к форуму [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .

## <a name="create-a-group-in-the-eac"></a>Создание группы в Центре администрирования Exchange

1. В Центре администрирования Exchange выберите **Получатели** \> **Группы**.

2. Нажмите кнопку **создать** ![значок](../media/ITPro-EAC-AddIcon.gif)добавить, а затем выберите **группу рассылки** или **группу безопасности**, в зависимости от ваших потребностей.

3. На странице **Новая группа рассылки** или **Новая группа безопасности** настройте указанные ниже параметры.

   - **Отображаемое имя**: введите понятное имя, которое является уникальным для Организации и имеет значение для пользователей EOP. Отображаемое имя является обязательным параметром.

   - **Псевдоним**: введите псевдоним группы длиной до 64 символов, уникальный для вашей организации. Пользователи EOP вводят псевдоним в строке "Кому:" сообщения электронной почты, и он сопоставляется с отображаемым именем группы. Если изменить псевдоним, основной SMTP-адрес группы также изменится и будет содержать новый псевдоним. Псевдоним является обязательным параметром.

   - **Описание**: введите описание группы, чтобы люди знали назначение этой группы.

   - **Владельцы**: по умолчанию владельцем является пользователь, который создает группу. Чтобы добавить владельца, нажмите кнопку **Добавить** ![значок](../media/ITPro-EAC-AddIcon.gif). Для каждой группы должен существовать по крайней мере один владелец.

     > [!NOTE]
     > Владельцы не обязательно должны быть членами группы.

   - **Members**: Используйте этот раздел, чтобы добавить участников группы и указать, требуется ли утверждение для пользователей присоединения к группе или выхода из нее. Чтобы добавить участников в группу, нажмите кнопку **Добавить** ![значок](../media/ITPro-EAC-AddIcon.gif).

4. Нажмите кнопку **ОК**, чтобы вернуться на исходную страницу.

5. Закончив, нажмите кнопку **Сохранить**, чтобы создать группу. Новая группа должна отобразиться в списке групп.

## <a name="edit-or-remove-a-group-in-the-eac"></a>Изменение или удаление группы в Центре администрирования Exchange

1. В Центре администрирования Exchange последовательно выберите пункты **Получатели** \> **Группы**.

2. Выполните одно из следующих действий:

   - Чтобы изменить группу, выберите группу, которую нужно просмотреть или изменить, и нажмите кнопку **изменить** ![значок](../media/ITPro-EAC-EditIcon.gif)редактирования. Вы можете обновлять Общие параметры, добавлять и удалять владельцев групп, а также добавлять и удалять участников групп по мере необходимости.

   - Чтобы удалить группу, выберите группу и нажмите кнопку **Удалить** ![значок](../media/ITPro-EAC-RemoveIcon.gif)"Удалить".

3. После внесения изменений нажмите кнопку **Сохранить**.

## <a name="create-edit-or-remove-a-group-using-remote-windows-powershell"></a>Создание, изменение или удаление группы с помощью удаленной консоли Windows PowerShell

В этом разделе представлены сведения о создании групп и изменении их свойств в Exchange Online Protection PowerShell. В нем также рассказывается об удалении существующей группы.

### <a name="create-a-group-using-remote-windows-powershell"></a>Создание группы с помощью удаленной оболочки Windows PowerShell

В этом примере командлет [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup) используется для создания группы рассылки с псевдонимом "itadmin" и именем "ИТ-администраторы". Кроме того, он добавляет пользователей как членов группы.

```PowerShell
New-EOPDistributionGroup -Type Distribution -Name "IT Administrators" -Alias itadmin -Members @("Member1","Member2","Member3") -ManagedBy Member1
```

**Note**: чтобы создать группу безопасности вместо группы рассылки, используйте значение `Security` параметра *Type* .

Чтобы убедиться, что группа "ИТ Administrators" успешно создана, выполните следующую команду, чтобы отобразить сведения о новой группе:

```PowerShell
Get-Recipient "IT Administrators" | Format-List
```

Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient).

Чтобы получить список членов группы, выполните следующую команду:

```PowerShell
Get-DistributionGroupMember "IT Administrators"
```

Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember).

Чтобы получить полный список всех групп, выполните следующую команду:

```PowerShell
Get-Recipient -RecipientType "MailUniversalDistributionGroup" | Format-Table | more
```

### <a name="change-the-properties-of-a-group-using-remote-windows-powershell"></a>Изменение свойств группы с помощью удаленной оболочки Windows PowerShell

Преимуществом использования PowerShell вместо центра администрирования Exchange является возможность изменения свойств нескольких групп.

Ниже приведено несколько примеров использования Exchange Online Protection PowerShell для изменения свойств групп.

В этом примере используются изменения основного SMTP-адреса (также называемого адресом ответа) для группы Employees в Сиэтле до sea.employees@contoso.com.

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

Подробные сведения о синтаксисе и параметрах можно найти в статье [Set – eopdistributiongroup используется](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup).

Чтобы убедиться, что вы успешно изменили свойства группы, выполните следующую команду, чтобы проверить новое значение:

```PowerShell
Get-Recipient "Seattle Employees" | Format-List "PrimarySmtpAddress"
```

В этом примере обновляются все участники группы Employees в Сиэтле. Разделяйте всех членов запятой.

```PowerShell
Update-EOPDistributionGroupMember -Identity "Seattle Employees" -Members @("Member1","Member2","Member3","Member4","Member5")
```

Подробные сведения о синтаксисе и параметрах можно найти в [статье Update – еопдистрибутионграупмембер](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember).

Чтобы получить список всех участников группы сотрудники в Сиэтле, выполните следующую команду:

```PowerShell
Get-DistributionGroupMember "Seattle Employees"
```

### <a name="remove-a-group-using-remote-windows-powershell"></a>Удаление группы с помощью удаленной оболочки Windows PowerShell

В этом примере показано, как удалить группу рассылки с именем IT Administrators.

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

Подробные сведения о синтаксисе и параметрах можно найти в статье [Remove – eopdistributiongroup используется](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup).

Чтобы убедиться, что группа удалена, выполните следующую команду и убедитесь, что группа (в данном случае "ИТ-администраторы") удалена.

```PowerShell
Get-Recipient -RecipientType "MailUniversalDistributionGroup"
```
