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
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: Сводка. Управляйте изолированным сайтом группы SharePoint Online с помощью этих процедур.
ms.openlocfilehash: 59c86c869ed38c3e64ff19974660cf96ec4c715e
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599006"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a>Управление изолированным сайтом группы SharePoint Online

 **Сводка.** Управляйте изолированным сайтом группы SharePoint Online с помощью этих процедур.
  
В этой статье описаны основные операции по управлению изолированным сайтом группы SharePoint Online.
  
## <a name="add-a-new-user"></a>Добавление нового пользователя

Когда к сайту присоединяется новый участник, необходимо определить его роль.
  
- Администрирование: добавьте новую учетную запись пользователя в группу доступа "Администраторы сайта".
    
- Активная совместная работа: добавьте учетную запись пользователя в группу доступа "Участники сайта".
    
- Просмотр: добавьте учетную запись пользователя в группу доступа "Посетители сайта".
    
Если вы управляете учетными записями и группами пользователей с помощью доменных служб Active Directory (AD DS), добавьте соответствующих пользователей в соответствующие группы доступа, используя обычные процедуры управления пользователями и группами AD DS, и дождитесь синхронизации с Office 365 подписки.
  
Если вы управляете учетными записями и группами пользователей с помощью Office 365, вы можете использовать центр администрирования Microsoft 365 или Microsoft PowerShell:
  
- Для центра администрирования Microsoft 365 войдите с помощью учетной записи пользователя, которой назначена роль администратора учетной записи пользователя или администратора организации, и используйте группы, чтобы добавить соответствующих пользователей в соответствующие группы доступа.
    
- Для PowerShell сначала [подключитесь к модулю PowerShell Azure Active Directory PowerShell для Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module). Чтобы добавить учетную запись пользователя в группу доступа по имени участника-пользователя (UPN), используйте следующий блок команд PowerShell:
    
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
    
Если вы управляете учетными записями и группами пользователей с помощью доменных служб Active Directory, добавьте соответствующие группы в соответствующие группы, используя обычные процедуры управления пользователями и группами AD DS, и дождитесь синхронизации с подпиской на Office 365.
  
Если вы управляете учетными записями и группами пользователей с помощью Office 365, вы можете использовать центр администрирования Microsoft 365 или PowerShell:
  
- Для центра администрирования Microsoft 365 войдите в систему, используя учетную запись пользователя, которой назначена роль администратора учетных записей или администратора организации, и используйте группы для добавления соответствующих групп в соответствующие группы доступа.
    
- Для PowerShell сначала [подключитесь к модулю PowerShell Azure Active Directory PowerShell для Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).
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
    
Если вы управляете учетными записями и группами пользователей с помощью доменных служб Active Directory, удалите соответствующих пользователей из соответствующих групп доступа, используя обычные процедуры управления пользователями и группами AD DS, и дождитесь синхронизации с подпиской на Office 365.
  
Если вы управляете учетными записями и группами пользователей с помощью Office 365, вы можете использовать центр администрирования Microsoft 365 или PowerShell:
  
- Для центра администрирования Microsoft 365 войдите с помощью учетной записи пользователя, которой назначена роль администратора учетной записи пользователя или администратора организации, и используйте группы для удаления соответствующих пользователей из соответствующих групп доступа.
    
- Для PowerShell сначала [подключитесь к модулю PowerShell Azure Active Directory PowerShell для Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).
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
    
Если вы управляете учетными записями и группами пользователей с помощью Windows Server Active Directory, удалите соответствующие группы из соответствующих групп доступа, используя обычные процедуры управления пользователями и группами AD DS, и дождитесь синхронизации с Office 365 подписки.
  
Если вы управляете учетными записями и группами пользователей с помощью Office 365, вы можете использовать центр администрирования Microsoft 365 или PowerShell:
  
- Для центра администрирования Microsoft 365 войдите с помощью учетной записи пользователя, которой назначена роль администратора учетной записи пользователя или администратора организации, и используйте группы для удаления соответствующих групп из соответствующих групп доступа.
    
- Для PowerShell сначала [подключитесь к модулю PowerShell Azure Active Directory PowerShell для Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).    
Чтобы удалить группу из группы доступа по отображаемому имени, используйте следующий блок команд PowerShell:
    
```powershell
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a>Создание вложенной папки документов с настраиваемыми разрешениями

Группе людей, работающих на изолированном сайте, может потребоваться закрытое место для совместной работы. В SharePoint Online вы можете создать вложенную папку в папке сайта "Документы" и назначить ей особые разрешения. Пользователи без разрешений не увидят эту папку.
  
Чтобы создать вложенную папку документов с настраиваемыми разрешениями, сделайте следующее:
  
1. Войдите в Office 365, используя учетную запись, состоящую в группе доступа "Администраторы" для сайта. Справочные материалы см. в статье [Вход в Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4).
    
2. Перейдите к изолированному сайту группы и нажмите **Документы**.
    
3. В папке "Документы" перейдите к нужной папке, создайте вложенную папку для настраиваемых разрешений и откройте ее.
    
4. Щелкните **Общий доступ**.
    
5. Нажмите **Доступ > Дополнительно**.
    
6. Нажмите **Прекратить наследование разрешений**, а затем нажмите кнопку **ОК**.
    
7. Щелкните **Общий доступ**.
    
8. Нажмите **Доступ > Дополнительно**.
    
9. Нажмите **Предоставить разрешения > Доступ > Дополнительно**.
    
10. На странице разрешений выберите **\<имя сайта> Участники в списке**.
    
11. На странице **\<имя сайта> Участники** установите флажок рядом с группой доступа "Участники сайта", выберите **Действия** > **Удалить пользователей из группы** и нажмите кнопку **ОК**.
    
12. Чтобы добавить участников в эту вложенную папку, нажмите **Создать > Добавить пользователей**.
    
13. В диалоговом окне **Общий доступ** введите имена учетных записей пользователей, которые могут совместно работать над файлами в папке, и нажмите кнопку **Поделиться**.
    
14. Обновите веб-страницу, чтобы увидеть новые результаты.
    
15. В области навигации слева выберите группу **\<имя сайта> Посетители** в разделе **Группы** и выполните действия 11–14, чтобы указать учетные записи пользователей, которые могут просматривать файлы во вложенной папке.
    
16. В области навигации слева выберите группу **\<имя сайта> -Владельцы** в разделе **Группы** и выполните действия 11–14, чтобы указать учетные записи пользователей, которые могут управлять разрешениями во вложенной папке.
    
17. Закройте вкладку **Пользователи и группы** в браузере.
    
## <a name="see-also"></a>См. также

[Изолированные сайты групп SharePoint Online](isolated-sharepoint-online-team-sites.md)
  
[Разработка изолированного сайта группы SharePoint Online](design-an-isolated-sharepoint-online-team-site.md)

[Развертывание изолированного сайта группы SharePoint Online](deploy-an-isolated-sharepoint-online-team-site.md)



