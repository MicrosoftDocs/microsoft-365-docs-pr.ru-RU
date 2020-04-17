---
title: Установка бессрочных пользовательских паролей
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466
description: Сведения о том, как задать срок действия отдельных паролей для отдельных пользователей с помощью Windows PowerShell.
ms.openlocfilehash: 2645e6d5f307a5e5ce8fab5f3a848bf4a539b031
ms.sourcegitcommit: 4988934836eee45c890b9bdd5ef73590656c78ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2020
ms.locfileid: "43540895"
---
# <a name="set-an-individual-users-password-to-never-expire"></a>Установка бессрочных пользовательских паролей

## <a name="set-the-password-expiration-policy-for-your-organization"></a>Установка политики срока действия паролей в организации

1. В центре администрирования перейдите на страницу **Параметры** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">безопасности & конфиденциальность</a> .
2. Рядом с полем **Политика паролей** выберите команду **изменить**. 
3. Если срок действия паролей не ограничен, установите переключатель в значение **выкл**. Вы получите возможность указать количество дней до истечения срока действия паролей.

## <a name="set-the-password-expiration-policy-for-individual-users"></a>Настройка политики истечения срока действия паролей для отдельных пользователей

Глобальный администратор облачной службы Майкрософт может использовать [PowerShell Azure Active Directory для Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) , чтобы задать неограниченный срок действия паролей для определенных пользователей. Кроме того, вы можете использовать командлеты [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) , чтобы удалить конфигурацию с неограниченным сроком действия или убедиться, что срок действия паролей пользователей неограничен.

Это руководство относится к другим поставщикам, таким как Intune и Office 365, которые также основываются на Azure AD для удостоверений и служб каталогов. Срок действия пароля является единственной частью политики, которую можно изменить.

Для получения дополнительных сведений об Azure AD PowerShell для Graph, обратитесь [к статье Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0).

> [!NOTE]
> Срок действия только паролей для учетных записей пользователей, которые не синхронизируются с помощью синхронизации службы каталогов, может быть запрещен. Дополнительные сведения о синхронизации службы каталогов можно найти [в статье Connect AD with Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).

### <a name="how-to-check-the-expiration-policy-for-a-password"></a>Проверка политики истечения срока действия для пароля

Дополнительные сведения о команде Get – AzureADUser в модуле AzureAD можно найти в справочной статье [Get/AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).

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

- Чтобы получить отчет обо всех пользователях с PasswordNeverExpires в HTML-коде на рабочем столе текущего пользователя с именем **репортпассвордневерекспирес. HTML**

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- Получение отчета обо всех пользователях с PasswordNeverExpires в CSV на рабочем столе текущего пользователя с именем **репортпассвордневерекспирес. csv**

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv
    ```

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

### <a name="set-a-password-to-never-expire"></a>Установка срока действия пароля не ограничена

Выполните одну из следующих команд:

- Чтобы задать срок действия пароля одного пользователя, выполните следующий командлет с помощью имени участника-пользователя или идентификатора пользователя:

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration
    ```

- Чтобы запретить срок действия паролей для всех пользователей в Организации, выполните следующий командлет:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> Для `-PasswordPolicies DisablePasswordExpiration` паролей устанавливается срок хранения, `pwdLastSet` основанный на атрибуте. Если вы настроили пароли пользователей, срок действия которых не истечет, а затем — срок действия паролей — 90 + дн. В зависимости от `pwdLastSet` атрибута, если вы измените срок действия на `-PasswordPolicies None`, то все пароли, имеющие `pwdLastSet` старше 90 дней, должны изменить их при следующем входе в систему. Это изменение может повлиять на большое количество пользователей.
