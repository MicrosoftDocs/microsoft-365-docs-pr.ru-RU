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
description: Воехайте в свой Microsoft 365 учетную запись администратора, чтобы установить некоторые отдельные пароли пользователей, чтобы никогда не истекать с помощью Windows PowerShell.
ms.openlocfilehash: 0747e0bfe8a7389db554d5d6a7f685605e013306
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571929"
---
# <a name="set-an-individual-users-password-to-never-expire"></a>Установка бессрочных пользовательских паролей

В этой статье объясняется, как установить пароль для отдельного пользователя, чтобы не истекать. Вы должны выполнить эти шаги с помощью PowerShell.

## <a name="before-you-begin"></a>Прежде чем начать

Эта статья адресована тем, кто устанавливает политику срока действия паролей в компании, учебном заведении или некоммерческой организации. Чтобы выполнить эти действия, вам нужно войти с помощью своей учетной записи администратора Microsoft 365. [Что такое учетная запись администратора?](../../business-video/admin-center-overview.md) 

Вы должны быть глобальным [администратором или администратором паролей](about-admin-roles.md) для выполнения этих шагов.

Глобальный администратор облачного сервиса Майкрософт может использовать [Azure Active Directory PowerShell для Graph](/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) для настройки паролей, срок действия которых не истекает для конкретных пользователей. Вы также можете использовать [cmdlets AzureAD](/powershell/module/Azuread) для удаления никогда не истекать конфигурации или посмотреть, какие пароли пользователей установлены никогда не истекает.

Это руководство распространяется на других поставщиков, таких как Intune и Microsoft 365, которые также полагаются на Azure AD для служб идентификации и каталогов. Срок действия пароля является единственной частью политики, которая может быть изменена.

> [!NOTE]
> Только пароли для учетных записей пользователей, которые не синхронизированы с помощью синхронизации каталога, могут быть настроены, чтобы не истекать. Для получения дополнительной информации о синхронизации каталогов [см. Подключение нашей эры с Azure AD](/azure/active-directory/connect/active-directory-aadconnect).

## <a name="how-to-check-the-expiration-policy-for-a-password"></a>Как проверить полис действия пароля

Для получения дополнительной информации о Get-AzureADUser команды в модуле [](/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0)AzureAD, см.

Выполните одну из следующих команд:

- Чтобы узнать, никогда не истечет ли срок действия пароля одного пользователя, запустите следующий cmdlet с помощью UPN *(например, user@contoso.onmicrosoft.com*) или идентификатора пользователя, который вы хотите проверить:

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

- Чтобы увидеть, что **срок действия пароля никогда** не истекает для всех пользователей, запустите следующий cmdlet:

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

- Чтобы получить отчет всех пользователей с PasswordNeverExpires в CSV на рабочем столе текущего пользователя с именем **ReportPasswordNeverExpires.csv**

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

- Чтобы установить пароли всех пользователей в организации, чтобы никогда не истекать, запустите следующий cmdlet:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> Учетные записи пользователей, настроенные с `-PasswordPolicies DisablePasswordExpiration` параметром, все еще стареют на основе `pwdLastSet` атрибута. На основании `pwdLastSet` атрибута, если вы измените срок `-PasswordPolicies None` действия, все пароли, которые имеют pwdLastSet старше 90 дней требуют, чтобы пользователь изменил их при следующем встраивом. Это изменение может повлиять на большое количество пользователей.

### <a name="set-a-password-to-expire"></a>Установить пароль для истечения срока действия

Выполните одну из следующих команд:

- Чтобы установить пароль одного пользователя, чтобы срок действия пароля истек, запустите следующий cmdlet с помощью UPN или идентификатор пользователя пользователя:

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- Чтобы установить пароли всех пользователей в организации, чтобы они истекли, используйте следующий cmdlet:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

## <a name="related-content"></a>Связанные материалы

[Предоставление пользователям прав на самостоятельный сброс пароля](../add-users/let-users-reset-passwords.md) (статья)

[Сброс паролей](../add-users/reset-passwords.md) (статья)