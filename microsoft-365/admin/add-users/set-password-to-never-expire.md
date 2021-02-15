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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466
description: Узнайте, как установить срок действия некоторых паролей отдельных пользователей с помощью Windows PowerShell.
ms.openlocfilehash: 2d60a8312be070d3f56cfef7cfb93e6c5da32991
ms.sourcegitcommit: e53234b1f64ebca00e121da1706c02b3337c35f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2020
ms.locfileid: "49580641"
---
# <a name="set-an-individual-users-password-to-never-expire"></a>Установка бессрочных пользовательских паролей

В этой статье объясняется, как установить срок действия пароля для отдельного пользователя. Эти действия необходимо выполнить с помощью PowerShell.

## <a name="before-you-begin"></a>Прежде чем начать

Эта статья адресована тем, кто устанавливает политику срока действия паролей в компании, учебном заведении или некоммерческой организации. Чтобы выполнить эти действия, вам нужно войти с помощью своей учетной записи администратора Microsoft 365. [Что такое учетная запись администратора?](../admin-overview/admin-overview.md) 

Для выполнения этих действий [необходимо быть](about-admin-roles.md) глобальным администратором или администратором паролей.

Глобальный администратор облачной службы Майкрософт может использовать [Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) для Graph, чтобы установить срок действия паролей для определенных пользователей. Кроме того, с помощью cmdlets [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) можно удалить конфигурацию, срок действия которой не истекает, или узнать, какие пароли пользователей имеют срок действия.

Это руководство применимо к другим поставщикам, таким как Intune и Microsoft 365, которые также используют Azure AD для удостоверений и служб каталогов. Срок действия пароля — единственная часть политики, которую можно изменить.

> [!NOTE]
> Можно настроить срок действия только паролей для учетных записей пользователей, которые не синхронизируются с помощью синхронизации каталогов. Дополнительные сведения о синхронизации службы каталогов см. в подключении [AD к Azure AD.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)

## <a name="how-to-check-the-expiration-policy-for-a-password"></a>Проверка политики истечения срока действия пароля

Дополнительные сведения о команде Get-AzureADUser в модуле AzureAD см. в справочной статье [Get-AzureADUser.](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0)

Выполните одну из следующих команд:

- Чтобы узнать, установлен ли срок действия пароля одного пользователя, запустите следующий cmdlet с помощью upN (например, *user@contoso.onmicrosoft.com)* или ИД пользователя, которого вы хотите проверить:

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

- Чтобы увидеть, **что** срок действия пароля не истекает для всех пользователей, запустите следующий cmdlet:

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- Чтобы получить отчет о всех пользователях с passwordNeverExpires в Html на рабочем столе текущего пользователя с именем  **ReportPasswordNeverExpires.html**

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- Чтобы получить отчет о всех пользователях с passwordNeverExpires в CSV на рабочем столе текущего пользователя с именем **ReportPasswordNeverExpires.csv**

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

- Чтобы установить срок действия паролей всех пользователей в организации, запустите следующий cmdlet:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> Учетные записи пользователей, настроенные с `-PasswordPolicies DisablePasswordExpiration` параметром, по-прежнему стареют в зависимости от `pwdLastSet` атрибута. В зависимости от этого атрибута при изменении срока действия на все пароли с pwdLastSet старше 90 дней пользователь должен изменить их при следующем `pwdLastSet` `-PasswordPolicies None` входе. Это изменение может повлиять на большое количество пользователей.

### <a name="set-a-password-to-expire"></a>Настройка срока действия пароля

Выполните одну из следующих команд:

- Чтобы установить пароль одного пользователя, чтобы срок действия пароля истек, запустите следующий cmdlet с использованием upN или ИД пользователя:

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- Чтобы установить пароли всех пользователей в организации, чтобы срок их действия истекал, используйте следующий cmdlet:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

## <a name="related-content"></a>Связанные материалы

[Предоставление пользователям прав на самостоятельный сброс пароля](../add-users/let-users-reset-passwords.md)

[Сброс паролей](../add-users/reset-passwords.md)