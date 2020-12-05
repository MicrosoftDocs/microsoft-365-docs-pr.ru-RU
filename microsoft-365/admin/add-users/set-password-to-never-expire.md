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
description: Сведения о том, как задать срок действия отдельных паролей для отдельных пользователей с помощью Windows PowerShell.
ms.openlocfilehash: 2d60a8312be070d3f56cfef7cfb93e6c5da32991
ms.sourcegitcommit: e53234b1f64ebca00e121da1706c02b3337c35f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2020
ms.locfileid: "49580641"
---
# <a name="set-an-individual-users-password-to-never-expire"></a>Установка бессрочных пользовательских паролей

В этой статье объясняется, как настроить пароль для отдельного пользователя без ограничения срока действия. Необходимо выполнить эти действия с помощью PowerShell.

## <a name="before-you-begin"></a>Прежде чем начать

Эта статья адресована тем, кто устанавливает политику срока действия паролей в компании, учебном заведении или некоммерческой организации. Чтобы выполнить эти действия, вам нужно войти с помощью своей учетной записи администратора Microsoft 365. [Что такое учетная запись администратора?](../admin-overview/admin-overview.md) 

Для выполнения этих действий необходимо быть [глобальным администратором или администратором паролей](about-admin-roles.md) .

Глобальный администратор облачной службы Майкрософт может использовать [PowerShell Azure Active Directory для Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) , чтобы задать неограниченный срок действия паролей для определенных пользователей. Кроме того, вы можете использовать командлеты [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) , чтобы удалить конфигурацию с неограниченным сроком действия или убедиться, что срок действия паролей пользователей неограничен.

Это руководство относится к другим поставщикам, таким как Intune и Microsoft 365, которые также основываются на Azure AD для идентификации и служб каталогов. Срок действия пароля является единственной частью политики, которую можно изменить.

> [!NOTE]
> Срок действия только паролей для учетных записей пользователей, которые не синхронизируются с помощью синхронизации службы каталогов, может быть запрещен. Дополнительные сведения о синхронизации службы каталогов можно найти [в статье Connect AD with Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).

## <a name="how-to-check-the-expiration-policy-for-a-password"></a>Проверка политики истечения срока действия для пароля

Для получения дополнительных сведений о команде Get-AzureADUser в модуле AzureAD, обратитесь к справочной статье [Get – AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).

Выполните одну из следующих команд:

- Чтобы убедиться, что срок действия пароля одного пользователя не ограничен, выполните следующий командлет с помощью имени участника-пользователя (например, *user@contoso.onmicrosoft.com*) или идентификатора пользователя, которого вы хотите проверить:

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    Пример:

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- Чтобы увидеть, что параметр **Password не истечет срок действия** для всех пользователей, выполните следующий командлет:

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- Получение отчета обо всех пользователях с PasswordNeverExpires в HTML-коде на рабочем столе текущего пользователя с именем  **ReportPasswordNeverExpires.html**

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- Чтобы получить отчет обо всех пользователях с PasswordNeverExpires в CSV на рабочем столе текущего пользователя с именем **ReportPasswordNeverExpires.csv**

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

- Чтобы запретить срок действия паролей для всех пользователей в Организации, выполните следующий командлет:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> Учетные записи пользователей, настроенные с `-PasswordPolicies DisablePasswordExpiration` параметром, по-прежнему имеют срок действия на основе `pwdLastSet` атрибута. В зависимости от `pwdLastSet` атрибута, если вы измените срок действия на, то для `-PasswordPolicies None` всех паролей с пвдластсет старше 90 дней необходимо, чтобы пользователь изменил их при следующем входе. Это изменение может повлиять на большое количество пользователей.

### <a name="set-a-password-to-expire"></a>Установка срока действия пароля

Выполните одну из следующих команд:

- Чтобы задать пароль одного пользователя, чтобы срок действия пароля истек, выполните следующий командлет с помощью имени участника-пользователя или идентификатора пользователя:

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- Чтобы задать пароли всех пользователей в Организации, истечения срока их действия, используйте следующий командлет:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

## <a name="related-content"></a>Связанные материалы

[Предоставление пользователям прав на самостоятельный сброс пароля](../add-users/let-users-reset-passwords.md)

[Сброс паролей](../add-users/reset-passwords.md)