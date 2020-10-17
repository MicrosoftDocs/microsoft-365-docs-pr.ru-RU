---
title: Установка бессрочных пользовательских паролей
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466
description: Сведения о том, как задать срок действия отдельных паролей для отдельных пользователей с помощью Windows PowerShell.
ms.openlocfilehash: e778ad8a020a6767934d51f8bc227bfc39b13a9b
ms.sourcegitcommit: 3165329d1fb5a7fd866ff287bea3b6354ea2be18
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580920"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="f266c-103">Установка бессрочных пользовательских паролей</span><span class="sxs-lookup"><span data-stu-id="f266c-103">Set an individual user's password to never expire</span></span>

<span data-ttu-id="f266c-104">В этой статье объясняется, как настроить пароль для отдельного пользователя без ограничения срока действия.</span><span class="sxs-lookup"><span data-stu-id="f266c-104">This article explains how to set a password for an individual user to not expire.</span></span> <span data-ttu-id="f266c-105">Необходимо выполнить эти действия с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f266c-105">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f266c-106">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="f266c-106">Before you begin</span></span>

<span data-ttu-id="f266c-107">Эта статья адресована тем, кто устанавливает политику срока действия паролей в компании, учебном заведении или некоммерческой организации.</span><span class="sxs-lookup"><span data-stu-id="f266c-107">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="f266c-108">Чтобы выполнить эти действия, вам нужно войти с помощью своей учетной записи администратора Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f266c-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="f266c-109">[Что такое учетная запись администратора?](../admin-overview/admin-overview.md)</span><span class="sxs-lookup"><span data-stu-id="f266c-109">[What's an admin account?](../admin-overview/admin-overview.md).</span></span> 

<span data-ttu-id="f266c-110">Для выполнения этих действий необходимо быть [глобальным администратором или администратором паролей](about-admin-roles.md) .</span><span class="sxs-lookup"><span data-stu-id="f266c-110">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="f266c-111">Глобальный администратор облачной службы Майкрософт может использовать [PowerShell Azure Active Directory для Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) , чтобы задать неограниченный срок действия паролей для определенных пользователей.</span><span class="sxs-lookup"><span data-stu-id="f266c-111">A global admin for a Microsoft cloud service can use the [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) to set passwords not to expire for specific users.</span></span> <span data-ttu-id="f266c-112">Кроме того, вы можете использовать командлеты [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) , чтобы удалить конфигурацию с неограниченным сроком действия или убедиться, что срок действия паролей пользователей неограничен.</span><span class="sxs-lookup"><span data-stu-id="f266c-112">You can also use [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span>

<span data-ttu-id="f266c-113">Это руководство относится к другим поставщикам, таким как Intune и Microsoft 365, которые также основываются на Azure AD для идентификации и служб каталогов.</span><span class="sxs-lookup"><span data-stu-id="f266c-113">This guide applies to other providers, such as Intune and Microsoft 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="f266c-114">Срок действия пароля является единственной частью политики, которую можно изменить.</span><span class="sxs-lookup"><span data-stu-id="f266c-114">Password expiration is the only part of the policy that can be changed.</span></span>

> [!NOTE]
> <span data-ttu-id="f266c-115">Срок действия только паролей для учетных записей пользователей, которые не синхронизируются с помощью синхронизации службы каталогов, может быть запрещен.</span><span class="sxs-lookup"><span data-stu-id="f266c-115">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="f266c-116">Дополнительные сведения о синхронизации службы каталогов можно найти [в статье Connect AD with Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="f266c-116">For more information about directory synchronization, see [Connect AD with Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>

## <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="f266c-117">Проверка политики истечения срока действия для пароля</span><span class="sxs-lookup"><span data-stu-id="f266c-117">How to check the expiration policy for a password</span></span>

<span data-ttu-id="f266c-118">Для получения дополнительных сведений о команде Get-AzureADUser в модуле AzureAD, обратитесь к справочной статье [Get – AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span><span class="sxs-lookup"><span data-stu-id="f266c-118">For more information about the Get-AzureADUser command in the AzureAD module, see the reference article [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span></span>

<span data-ttu-id="f266c-119">Выполните одну из следующих команд:</span><span class="sxs-lookup"><span data-stu-id="f266c-119">Run one of the following commands:</span></span>

- <span data-ttu-id="f266c-120">Чтобы убедиться, что срок действия пароля одного пользователя не ограничен, выполните следующий командлет с помощью имени участника-пользователя (например, *user@contoso.onmicrosoft.com*) или идентификатора пользователя, которого вы хотите проверить:</span><span class="sxs-lookup"><span data-stu-id="f266c-120">To see if a single user's password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    <span data-ttu-id="f266c-121">Пример:</span><span class="sxs-lookup"><span data-stu-id="f266c-121">Example:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- <span data-ttu-id="f266c-122">Чтобы увидеть, что параметр **Password не истечет срок действия** для всех пользователей, выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="f266c-122">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- <span data-ttu-id="f266c-123">Получение отчета обо всех пользователях с PasswordNeverExpires в HTML-коде на рабочем столе текущего пользователя с именем  **ReportPasswordNeverExpires.html**</span><span class="sxs-lookup"><span data-stu-id="f266c-123">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- <span data-ttu-id="f266c-124">Чтобы получить отчет обо всех пользователях с PasswordNeverExpires в CSV на рабочем столе текущего пользователя с именем **ReportPasswordNeverExpires.csv**</span><span class="sxs-lookup"><span data-stu-id="f266c-124">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>

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

- <span data-ttu-id="f266c-125">Чтобы запретить срок действия паролей для всех пользователей в Организации, выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="f266c-125">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

### <a name="set-a-password-to-expire"></a><span data-ttu-id="f266c-126">Установка срока действия пароля</span><span class="sxs-lookup"><span data-stu-id="f266c-126">Set a password to expire</span></span>

<span data-ttu-id="f266c-127">Выполните одну из следующих команд:</span><span class="sxs-lookup"><span data-stu-id="f266c-127">Run one of the following commands:</span></span>

- <span data-ttu-id="f266c-128">Чтобы задать пароль одного пользователя, чтобы срок действия пароля истек, выполните следующий командлет с помощью имени участника-пользователя или идентификатора пользователя:</span><span class="sxs-lookup"><span data-stu-id="f266c-128">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- <span data-ttu-id="f266c-129">Чтобы задать пароли всех пользователей в Организации, истечения срока их действия, используйте следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="f266c-129">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

> [!WARNING]
> <span data-ttu-id="f266c-130">Учетные записи пользователей, настроенные с `-PasswordPolicies DisablePasswordExpiration` параметром, по-прежнему возрастются на основе `pwdLastSet` атрибута учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="f266c-130">User accounts configured with the `-PasswordPolicies DisablePasswordExpiration` parameter still age based on the `pwdLastSet` user account attribute.</span></span> <span data-ttu-id="f266c-131">Например, если вы настроили пароли пользователей, срок действия которых не истечет, а затем — 90 или более дней, срок действия паролей не истечет.</span><span class="sxs-lookup"><span data-stu-id="f266c-131">For example, if you set user passwords to never expire and then 90 or more days go by, the passwords still expire.</span></span> <span data-ttu-id="f266c-132">На основе `pwdLastSet` атрибута учетной записи пользователя для учетных записей пользователей, настроенных с помощью этого `-PasswordPolicies None` параметра, все пароли, имеющие `pwdLastSet` старше 90 дней, должны изменить их при следующем входе в систему. Это изменение может повлиять на большое количество пользователей.</span><span class="sxs-lookup"><span data-stu-id="f266c-132">Based on the `pwdLastSet` user account attribute, for user accounts configured with the `-PasswordPolicies None` parameter, all passwords that have a `pwdLastSet` older than 90 days require the user to change them the next time they sign in.This change can affect a large number of users.</span></span>

## <a name="related-content"></a><span data-ttu-id="f266c-133">Связанные материалы</span><span class="sxs-lookup"><span data-stu-id="f266c-133">Related content</span></span>

[<span data-ttu-id="f266c-134">Предоставление пользователям прав на самостоятельный сброс пароля</span><span class="sxs-lookup"><span data-stu-id="f266c-134">Let users reset their own passwords</span></span>](../add-users/let-users-reset-passwords.md)

[<span data-ttu-id="f266c-135">Сброс паролей</span><span class="sxs-lookup"><span data-stu-id="f266c-135">Reset passwords</span></span>](../add-users/reset-passwords.md)