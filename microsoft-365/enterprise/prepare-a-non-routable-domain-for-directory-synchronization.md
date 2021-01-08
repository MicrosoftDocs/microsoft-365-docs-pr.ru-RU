---
title: Подготовка немаршрутизируемого домена к синхронизации службы каталогов
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365E_SetupDirSyncLocalDir
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: e7968303-c234-46c4-b8b0-b5c93c6d57a7
description: Узнайте, что делать, если у вас есть домен, не связанный с маршрутией, связанный с учетными записями локального пользователя, прежде чем синхронизировать их с клиентом Microsoft 365.
ms.openlocfilehash: dcd941bbae159afeb0cf6ef4f5acbaf409966295
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780336"
---
# <a name="prepare-a-non-routable-domain-for-directory-synchronization"></a>Подготовка немаршрутизируемого домена к синхронизации службы каталогов

При синхронизации локального каталога с Microsoft 365 необходимо иметь проверенный домен в Azure Active Directory (Azure AD). Синхронизируются только имена основных пользователей( UPNS), связанные с локального домена доменных служб Active Directory (AD DS). Однако любое имя upN, которое содержит нена маршрутизируемый домен, например ".local" (например, billa@contoso.local), будет синхронизировано с доменом .onmicrosoft.com (например: billa@contoso.onmicrosoft.com). 

Если в настоящее время вы используете "локальный" домен для учетных записей пользователей в доменных службах AD DS, рекомендуется изменить их на проверенный домен, например billa@contoso.com, для правильной синхронизации с доменом Microsoft 365.
  
## <a name="what-if-i-only-have-a-local-on-premises-domain"></a>Что делать, если у меня есть только локальный домен .local?

Azure AD Connect используется для синхронизации AD DS с клиентом Azure AD клиента Microsoft 365. Дополнительные сведения см. в интеграции локальной идентификации [с Azure AD.](https://docs.microsoft.com/azure/architecture/reference-architectures/identity/azure-ad)
  
Azure AD Connect синхронизирует upN и пароль пользователей, чтобы пользователи могли вводить те же учетные данные, что и локально. Однако Azure AD Connect синхронизирует пользователей только с доменами, проверенными Microsoft 365. Это означает, что домен также проверяется Службой Azure AD, так как удостоверениями Microsoft 365 управляет Azure AD. Другими словами, домен должен быть допустимым доменом Интернета (например, .com, .org, .net, .us). Если внутренняя служба доменных служб AD DS использует только домен, который не является маршрутивируемым (например, ".local"), это может не совпадать с проверенным доменом, который у вас есть для клиента Microsoft 365. Эту проблему можно устранить, изменив основной домен в локальной AD DS или добавив один или несколько суффиксов имени upN.
  
### <a name="change-your-primary-domain"></a>Изменение основного домена

Измените основной домен на домен, проверенный в Microsoft 365, например contoso.com. Каждый пользователь с доменом contoso.local затем обновляется до contoso.com. Однако это очень сложный процесс, и более простое решение описано в следующем разделе.
  
### <a name="add-upn-suffixes-and-update-your-users-to-them"></a>Добавление суффиксов upN и обновление пользователей

Чтобы решить проблему ".local", необходимо зарегистрировать новый суффикс или суффикс имени upN в доменных службах AD DS в соответствие с доменом (или доменами), проверенными в Microsoft 365. После регистрации нового суффикса имена пользователей обновляются, заменив имя ".local" новым именем домена, например, чтобы учетная запись пользователя выглядела billa@contoso.com.
  
После обновления имен upns для использования проверенного домена вы можете синхронизировать свои доменные службы AD DS с Microsoft 365.
  
#### <a name="step-1-add-the-new-upn-suffix"></a>Шаг 1. Добавление нового суффикса upN**
  
1. На контроллере домена AD DS  в диспетчере серверов выберите "Tools \> **Active Directory Domains and Trusts".**
    
    **Или, если у вас нет Windows Server 2012**
    
    Нажмите **клавиши Windows + R,** чтобы открыть диалоговое окно **"Выполнить",** а затем введите Domain.msc и нажмите кнопку **"ОК".**
    
    ![Выберите "Домены и доверие Active Directory".](../media/46b6e007-9741-44af-8517-6f682e0ac974.png)
  
2. В окне "Домены и доверие **Active Directory"** щелкните правой кнопкой мыши "Домены и доверие **Active Directory"** и выберите **"Свойства".**
    
    ![Щелкните правой кнопкой мыши домены и доверие Active Directory и выберите "Свойства"](../media/39d20812-ffb5-4ba9-8d7b-477377ac360d.png)
  
3. На вкладке "Суффиксы upN" в поле "Альтернативные суффиксы **upN"** введите новый суффикс или суффикс **upN,** а затем выберите "Добавить  \> **применить".**
    
    ![Добавление нового суффикса upN](../media/a4aaf919-7adf-469a-b93f-83ef284c0915.PNG)
  
    После **добавления** суффиксов выберите "ОК". 
    
 #### <a name="step-2-change-the-upn-suffix-for-existing-users"></a>Шаг 2. Изменение суффикса upN для существующих пользователей
  
1. На контроллере домена AD DS  в диспетчере серверов выберите "Средства active Directory — пользователи \> **и компьютеры".**
    
    **Или, если у вас нет Windows Server 2012**
    
    Нажмите **клавиши Windows + R,** чтобы открыть диалоговое окно **"Выполнить",** а затем введите Dsa.msc и нажмите кнопку **ОК**
    
2. Выберите пользователя, щелкните правой кнопкой мыши и выберите **"Свойства".**
    
3. На **вкладке "Учетная** запись" в выпадаемом списке суффиксов upN выберите новый суффикс и выберите **"ОК".**
    
    ![Добавление нового суффикса upN для пользователя](../media/54876751-49f0-48cc-b864-2623c4835563.png)
  
4. Выполните эти действия для каждого пользователя.
    
   
### <a name="use-powershell-to-change-the-upn-suffix-for-all-of-your-users"></a>Использование PowerShell для изменения суффикса upN для всех пользователей

Если у вас много учетных записей пользователей для обновления, проще использовать PowerShell. В следующем примере для изменения всех суффиксов contoso.local на contoso.com AD DS используются contoso.com [Get-ADUser](https://go.microsoft.com/fwlink/p/?LinkId=624312) и [Set-ADUser.](https://go.microsoft.com/fwlink/p/?LinkId=624313) 

Например, можно выполнить следующие команды PowerShell, чтобы обновить все суффиксы contoso.local до contoso.com:
    
  ```powershell
  $LocalUsers = Get-ADUser -Filter "UserPrincipalName -like '*contoso.local'" -Properties userPrincipalName -ResultSetSize $null
  $LocalUsers | foreach {$newUpn = $_.UserPrincipalName.Replace("@contoso.local","@contoso.com"); $_ | Set-ADUser -UserPrincipalName $newUpn}
  ```

Дополнительные Windows PowerShell active [Directory](https://go.microsoft.com/fwlink/p/?LinkId=624314) см. в Windows PowerShell AD DS. 

