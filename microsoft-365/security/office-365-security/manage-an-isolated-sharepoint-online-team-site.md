---
title: Управление изолированным сайтом группы SharePoint Online
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: Управляйте изолированным сайтом группы SharePoint Online, добавляйте новых пользователей и группы, удаляйте пользователей и группы, а также создавайте в подкадровку документов с пользовательскими разрешениями.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 20e354de77b70ea69d69e201bd3b1d40ea32cc5b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289525"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a>Управление изолированным сайтом группы SharePoint Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1)](office-365-atp.md)
- SharePoint Online 

 **Сводка.** Управляйте изолированным сайтом группы SharePoint Online с помощью этих процедур.

В этой статье описаны основные операции по управлению изолированным сайтом группы SharePoint Online.

## <a name="add-a-new-user"></a>Добавление нового пользователя

Когда к сайту присоединяется новый участник, необходимо определить его роль.

- Администрирование: добавьте новую учетную запись пользователя в группу доступа "Администраторы сайта".

- Активная совместная работа: добавьте учетную запись пользователя в группу доступа "Участники сайта".

- Просмотр: добавьте учетную запись пользователя в группу доступа "Посетители сайта".

Если вы управляете учетными записями пользователей и группами с помощью доменных служб Active Directory (AD DS), добавьте соответствующих пользователей в соответствующие группы доступа с помощью обычных процедур управления пользователями и группами AD DS и дождись синхронизации с подпиской.

Если вы управляете учетной записью пользователя и группами с помощью Microsoft 365, вы можете использовать Центр администрирования Microsoft 365 или Microsoft PowerShell:

- В Центре администрирования Microsoft 365 во sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate users to the appropriate access groups.

- Для PowerShell сначала подключите [модуль Azure Active Directory PowerShell для Graph.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module) Чтобы добавить учетную запись пользователя в группу доступа по имени участника-пользователя (UPN), используйте следующий блок команд PowerShell:

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

Чтобы добавить учетную запись пользователя в группу доступа по отображаемому имени, используйте следующий блок команд PowerShell:

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a>Добавление новой группы

Чтобы добавить доступ для всей группы, необходимо определить роль всех членов группы на сайте:

- Администрирование: добавьте группу в группу доступа "Администраторы сайта".

- Активная совместная работа: добавьте группу в группу доступа "Участники сайта".

- Просмотр: добавьте группу в группу доступа "Посетители сайта".

Если вы управляете учетными записями и группами пользователей с помощью AD DS, добавьте соответствующие группы в соответствующие группы с помощью обычных процедур управления пользователями и группами AD DS и дождись синхронизации с подпиской.

Если вы управляете учетной записью и группами пользователей с помощью Office 365, вы можете использовать Центр администрирования Microsoft 365 или PowerShell:

- В Центре администрирования Microsoft 365 во sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate groups to the appropriate access groups.

- Для PowerShell сначала подключите [модуль Azure Active Directory PowerShell для Graph.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
 Затем используйте следующие команды PowerShell:

```powershell
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a>Удаление пользователя

Чтобы закрыть доступ к сайту для пользователя, удалите его из группы доступа, в которой он в данный момент состоит.

- Администрирование: удалите учетную запись пользователя из группы доступа "Администраторы сайта".

- Активная совместная работа: удалите учетную запись пользователя из группы доступа "Участники сайта".

- Просмотр: удалите учетную запись пользователя из группы доступа "Посетители сайта".

Если вы управляете учетными записями и группами пользователей с помощью AD DS, удалите соответствующих пользователей из соответствующих групп доступа с помощью обычных процедур управления пользователями и группами AD DS и дождись синхронизации с подпиской.

Если вы управляете учетной записью и группами пользователей с помощью Office 365, вы можете использовать Центр администрирования Microsoft 365 или PowerShell:

- В Центре администрирования Microsoft 365 во sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate users from the appropriate access groups.

- Для PowerShell сначала подключите [модуль Azure Active Directory PowerShell для Graph.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
Чтобы удалить учетную запись пользователя из группы доступа по имени участника-пользователя, используйте следующий блок команд PowerShell:

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

Чтобы удалить учетную запись пользователя из группы доступа по отображаемому имени, используйте следующий блок команд PowerShell:

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a>Удаление группы

Чтобы закрыть доступ для всей группы, удалите ее из группы доступа, в которой она в данный момент состоит:

- Администрирование: удалите группу из группы доступа "Администраторы сайта".

- Активная совместная работа: удалите группу из группы доступа "Участники сайта".

- Просмотр: удалите группу из группы доступа "Посетители сайта".

Если вы управляете учетными записями и группами пользователей с помощью Windows Server Active Directory, удалите соответствующие группы из соответствующих групп доступа с помощью обычных процедур управления пользователями и группами AD DS и дождись синхронизации с подпиской.

Если вы управляете учетной записью и группами пользователей с помощью Office 365, вы можете использовать Центр администрирования Microsoft 365 или PowerShell:

- В Центре администрирования Microsoft 365 во sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate groups from the appropriate access groups.

- Для PowerShell сначала подключите [модуль Azure Active Directory PowerShell для Graph.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
Чтобы удалить группу из группы доступа по отображаемому имени, используйте следующий блок команд PowerShell:

```powershell
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a>Создание вложенной папки документов с настраиваемыми разрешениями

Группе людей, работающих на изолированном сайте, может потребоваться закрытое место для совместной работы. В SharePoint Online вы можете создать вложенную папку в папке сайта "Документы" и назначить ей особые разрешения. Пользователи без разрешений не увидят эту папку.

Чтобы создать вложенную папку документов с настраиваемыми разрешениями, сделайте следующее:

1. Во sign in to an account that is a member of the admins access group for the site. Справку см. в статье [Вход в Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).

2. Перейдите к изолированному сайту группы и нажмите **Документы**.

3. В папке "Документы" перейдите к нужной папке, создайте вложенную папку для настраиваемых разрешений и откройте ее.

4. Щелкните **Общий доступ**.

5. Нажмите **Доступ > Дополнительно**.

6. Нажмите **Прекратить наследование разрешений**, а затем нажмите кнопку **ОК**.

7. Щелкните **Общий доступ**.

8. Нажмите **Доступ > Дополнительно**.

9. Нажмите **Предоставить разрешения > Доступ > Дополнительно**.

10. On the permissions page, click **\<site name> Members in the list**.

11. На странице **\<site name> "Участники"** выберите контрольный знак рядом с группой доступа "Участники сайта", щелкните "Действия", "Удалить пользователей из группы" и нажмите кнопку **"ОК".**

12. Чтобы добавить участников в эту вложенную папку, нажмите **Создать > Добавить пользователей**.

13. В диалоговом окне **Общий доступ** введите имена учетных записей пользователей, которые могут совместно работать над файлами в папке, и нажмите кнопку **Поделиться**.

14. Обновите веб-страницу, чтобы увидеть новые результаты.

15. Under **Groups** in the left navigation, click the **\<site name> Visitors** group and use steps 11-14 to specify the set of user accounts that can view the files in the subfolder (as needed).

16. Under **Groups** in the left navigation, click the **\<site name> Owners** group and use steps 11-14 to specify the set of user accounts that can administer the permissions in the subfolder (as needed).

17. Закройте вкладку **Пользователи и группы** в браузере.

## <a name="see-also"></a>См. также

[Изолированные сайты групп SharePoint Online](isolated-sharepoint-online-team-sites.md)

[Разработка изолированного сайта группы SharePoint Online](design-an-isolated-sharepoint-online-team-site.md)

[Развертывание изолированного сайта группы SharePoint Online](deploy-an-isolated-sharepoint-online-team-site.md)
