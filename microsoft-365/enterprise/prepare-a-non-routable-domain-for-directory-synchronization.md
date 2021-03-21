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
description: Узнайте, что делать, если у вас есть неотъемлемый домен, связанный с учетными записями локального пользователя, прежде чем синхронизировать их с клиентом Microsoft 365.
ms.openlocfilehash: e4d0e020c5792c610d501c33e8f3d5131b7a1ff0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927400"
---
# <a name="prepare-a-non-routable-domain-for-directory-synchronization"></a>Подготовка немаршрутизируемого домена к синхронизации службы каталогов

При синхронизации локального каталога с Microsoft 365 необходимо иметь проверенный домен в Azure Active Directory (Azure AD). Синхронизируются только основные имена пользователей (UPNs), связанные с доменом Active Directory Domain Services (AD DS). Однако любой домен upN, содержащий домен, который не является маршрутизируемым, например ".local" (пример: billa@contoso.local), будет синхронизирован с доменом .onmicrosoft.com (пример: billa@contoso.onmicrosoft.com). 

Если в настоящее время используется домен ".local" для учетных записей пользователей в AD DS, рекомендуется изменить их на использование проверенного домена, например billa@contoso.com, для правильной синхронизации с доменом Microsoft 365.
  
## <a name="what-if-i-only-have-a-local-on-premises-domain"></a>Что делать, если у меня есть только локальный домен ".local"?

Вы используете Azure AD Connect для синхронизации AD DS с клиентом Azure AD клиента Microsoft 365. Дополнительные сведения см. в сайте Интеграция идентификаторов локальной системы [с Azure AD.](/azure/architecture/reference-architectures/identity/azure-ad)
  
Azure AD Connect синхронизирует upN и пароль пользователей, чтобы пользователи могли войти с одинаковыми учетными данными, которые они используют на месте. Однако Azure AD Connect синхронизирует пользователей только с доменами, проверенными Microsoft 365. Это означает, что домен также проверяется Azure AD, так как идентификаторы Microsoft 365 управляются Azure AD. Другими словами, домен должен быть допустимым доменом Интернета (например, .com, .org, .net, .us). Если во внутренней службе AD DS используется только нена маршрутируемый домен (например, ".local"), это не может совпадать с проверенным доменом, который у вас есть для клиента Microsoft 365. Эту проблему можно устранить, изменив основной домен в локальной AD DS или добавив один или несколько суффиксов upN.
  
### <a name="change-your-primary-domain"></a>Изменение основного домена

Измените основной домен на проверенный в Microsoft 365 домен, например contoso.com. Каждый пользователь с доменом contoso.local обновляется до contoso.com. Однако это очень сложный процесс, и более простое решение описано в следующем разделе.
  
### <a name="add-upn-suffixes-and-update-your-users-to-them"></a>Добавление суффиксов upN и обновление пользователей к ним

Проблему ".local" можно решить, зарегистрировав в AD DS новый суффикс или суффиксы upN, чтобы соответствовать домену (или доменам), проверенным в Microsoft 365. После регистрации нового суффикса обновляются пользовательские ИБН, чтобы заменить ".local" новым доменным именем, например, чтобы учетная запись пользователя выглядела как billa@contoso.com.
  
После обновления upNs для использования проверенного домена вы готовы синхронизировать локальное AD DS с Microsoft 365.
  
#### <a name="step-1-add-the-new-upn-suffix"></a>Шаг 1. Добавление нового суффикса upN**
  
1. На контроллере домена AD DS в диспетчере серверов выберите **Средства** \> **Active Directory Domains и Trusts.**
    
    **Или, если у вас нет Windows Server 2012**
    
    Нажмите **клавишу Windows + R,** чтобы открыть диалоговое окно **Run,** а затем введите домен.msc, а затем выберите **ОК**.
    
    ![Выберите домены Active Directory и трасты.](../media/46b6e007-9741-44af-8517-6f682e0ac974.png)
  
2. В **окне Active Directory Domains and Trusts** щелкните правой кнопкой мыши **Active Directory Domains and Trusts** и выберите **свойства**.
    
    ![Щелкните правой кнопкой мыши Домены и трасты Active Directory и выберите свойства](../media/39d20812-ffb5-4ba9-8d7b-477377ac360d.png)
  
3. На вкладке **UpN Suffixes** в поле Альтернативные Суффиксы UPN введите новый суффикс или суффиксЫ **upN,** а затем выберите **Добавить** \> **Применить**.
    
    ![Добавление нового суффикса upN](../media/a4aaf919-7adf-469a-b93f-83ef284c0915.PNG)
  
    Выберите **ОК,** когда вы закончили добавление суффиксов. 
    
 #### <a name="step-2-change-the-upn-suffix-for-existing-users"></a>Шаг 2. Изменение суффикса UPN для существующих пользователей
  
1. На контроллере домена AD DS в диспетчере серверов выберите **средства** \> **Active Directory Users and Computers.**
    
    **Или, если у вас нет Windows Server 2012**
    
    Нажмите **клавишу Windows + R,** чтобы открыть диалоговое окно **Run,** а затем введите в Dsa.msc и нажмите **кнопку ОК**
    
2. Выберите пользователя правой кнопкой мыши и выберите **Свойства.**
    
3. На **вкладке Учетная** запись в списке суффикса upN выберите новый суффикс upN, а затем выберите **ОК**.
    
    ![Добавление нового суффикса upN для пользователя](../media/54876751-49f0-48cc-b864-2623c4835563.png)
  
4. Выполните эти действия для каждого пользователя.
    
   
### <a name="use-powershell-to-change-the-upn-suffix-for-all-of-your-users"></a>Использование PowerShell для изменения суффикса UPN для всех пользователей

Если у вас много учетных записей пользователей для обновления, проще использовать PowerShell. В следующем примере для изменения всех суффиксов contoso.local на contoso.com AD DS используются cmdlets [Get-ADUser](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617241(v=technet.10)) и [Set-ADUser.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617215(v=technet.10)) 

Например, можно выполнить следующие команды PowerShell, чтобы обновить все суффиксы contoso.local до contoso.com:
    
  ```powershell
  $LocalUsers = Get-ADUser -Filter "UserPrincipalName -like '*contoso.local'" -Properties userPrincipalName -ResultSetSize $null
  $LocalUsers | foreach {$newUpn = $_.UserPrincipalName.Replace("@contoso.local","@contoso.com"); $_ | Set-ADUser -UserPrincipalName $newUpn}
  ```

Дополнительные Windows PowerShell active [Directory](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617195(v=technet.10)) см. в Windows PowerShell AD DS.