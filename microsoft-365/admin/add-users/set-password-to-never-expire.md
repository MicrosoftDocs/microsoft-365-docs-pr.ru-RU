---
title: Установка бессрочных пользовательских паролей
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466
description: Вопишите в свою учетную запись Microsoft 365 администратора, чтобы установить некоторые отдельные пароли пользователей, которые никогда не истекают с помощью Windows PowerShell.
ms.openlocfilehash: 29d0ebcbb3f9fb197e574731e23aaa64c2fa7894
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394259"
---
# <a name="set-an-individual-users-password-to-never-expire"></a>Установка бессрочных пользовательских паролей

В этой статье объясняется, как установить пароль для отдельного пользователя, чтобы срок действия не истек. Эти действия необходимо выполнить с помощью PowerShell.

## <a name="before-you-begin"></a>Прежде чем начать

Эта статья адресована тем, кто устанавливает политику срока действия паролей в компании, учебном заведении или некоммерческой организации. Чтобы выполнить эти действия, вам нужно войти с помощью своей учетной записи администратора Microsoft 365. [Что такое учетная запись администратора?](../../business-video/admin-center-overview.md)

Для выполнения этих [действий](about-admin-roles.md) необходимо быть глобальным администратором или администратором паролей.

Глобальный администратор облачной службы Майкрософт может использовать Azure Active Directory [PowerShell](/powershell/azure/active-directory/install-adv2) для Graph, чтобы установить пароли, срок действия которых не истекает для определенных пользователей. Вы также можете использовать [cmdlets AzureAD](/powershell/module/Azuread) для удаления конфигурации с истекшим сроком действия или для того, чтобы узнать, какие пароли пользователей не истекают.

Это руководство применяется к другим поставщикам, таким как Intune и Microsoft 365, которые также используют Azure AD для служб удостоверений и каталогов. Срок действия пароля — это единственная часть политики, которую можно изменить.


## <a name="how-to-check-the-expiration-policy-for-a-password"></a>Проверка политики истечения срока действия пароля

Дополнительные сведения о команде Get-AzureADUser в модуле AzureAD см. в справочной статье [Get-AzureADUser.](/powershell/module/Azuread/Get-AzureADUser)

Выполните одну из следующих команд:

- Чтобы узнать, не установлен ли срок действия пароля одного пользователя, запустите следующий cmdlet с помощью upN (например, *user@contoso.onmicrosoft.com)* или пользовательского ID пользователя, который необходимо проверить:

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    Пример.

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

- Чтобы параметр **Password никогда не истекал** для всех пользователей, запустите следующий cmdlet:

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- Чтобы получить отчет всех пользователей с PasswordNeverExpires в Html на рабочем столе текущего пользователя с  **именемReportPasswordNeverExpires.html**

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```

- Чтобы получить отчет всех пользователей с passwordNeverExpires в CSV на рабочем столе текущего пользователя с именем **ReportPasswordNeverExpires.csv**

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv

## Set a password to never expire

Run one of the following commands:

- To set the password of one user to never expire, run the following cmdlet by using the UPN or the user ID of the user:

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration
    ```

- Чтобы пароли всех пользователей организации никогда не истекли, запустите следующий cmdlet:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> Учетные записи пользователей, настроенные с `-PasswordPolicies DisablePasswordExpiration` параметром still age на основе `pwdLastSet` атрибута. В зависимости от атрибута, если срок действия меняется на, все пароли с pwdLastSet старше 90 дней требуют от пользователя изменить их при следующем `pwdLastSet` `-PasswordPolicies None` входе. Это изменение может повлиять на большое число пользователей.

### <a name="set-a-password-to-expire"></a>Установите срок действия пароля

Выполните одну из следующих команд:

- Чтобы установить пароль одного пользователя, чтобы срок действия пароля истек, запустите следующий комдлет с помощью upN или пользовательского ID пользователя:

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- Чтобы установить пароли всех пользователей в организации, чтобы они истекли, используйте следующий cmdlet:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

## <a name="related-content"></a>Связанные материалы

[Предоставление пользователям прав на самостоятельный сброс пароля](../add-users/let-users-reset-passwords.md) (статья)\
[Сброс паролей](../add-users/reset-passwords.md) (статья)\
[Установите политику истечения пароля для организации](../manage/set-password-expiration-policy.md) (статья)
