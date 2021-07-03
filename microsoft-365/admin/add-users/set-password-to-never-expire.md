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
description: Вопишите в свою учетную запись Microsoft 365 администратора, чтобы установить некоторые отдельные пароли пользователей, которые никогда не истекают с помощью Windows PowerShell.
ms.openlocfilehash: a0b247f4b736ecccab57398e1e7131f0a06a2958
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286277"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="2da3b-103">Установка бессрочных пользовательских паролей</span><span class="sxs-lookup"><span data-stu-id="2da3b-103">Set an individual user's password to never expire</span></span>

<span data-ttu-id="2da3b-104">В этой статье объясняется, как установить пароль для отдельного пользователя, чтобы срок действия не истек.</span><span class="sxs-lookup"><span data-stu-id="2da3b-104">This article explains how to set a password for an individual user to not expire.</span></span> <span data-ttu-id="2da3b-105">Эти действия необходимо выполнить с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2da3b-105">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="2da3b-106">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="2da3b-106">Before you begin</span></span>

<span data-ttu-id="2da3b-107">Эта статья адресована тем, кто устанавливает политику срока действия паролей в компании, учебном заведении или некоммерческой организации.</span><span class="sxs-lookup"><span data-stu-id="2da3b-107">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="2da3b-108">Чтобы выполнить эти действия, вам нужно войти с помощью своей учетной записи администратора Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2da3b-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="2da3b-109">[Что такое учетная запись администратора?](../../business-video/admin-center-overview.md)</span><span class="sxs-lookup"><span data-stu-id="2da3b-109">[What's an admin account?](../../business-video/admin-center-overview.md).</span></span>

<span data-ttu-id="2da3b-110">Для выполнения этих [действий](about-admin-roles.md) необходимо быть глобальным администратором или администратором паролей.</span><span class="sxs-lookup"><span data-stu-id="2da3b-110">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="2da3b-111">Глобальный администратор облачной службы Майкрософт может использовать Azure Active Directory [PowerShell](/powershell/azure/active-directory/install-adv2) для Graph, чтобы установить пароли, срок действия которых не истекает для определенных пользователей.</span><span class="sxs-lookup"><span data-stu-id="2da3b-111">A global admin for a Microsoft cloud service can use the [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2) to set passwords not to expire for specific users.</span></span> <span data-ttu-id="2da3b-112">Вы также можете использовать [cmdlets AzureAD](/powershell/module/Azuread) для удаления конфигурации с истекшим сроком действия или для того, чтобы узнать, какие пароли пользователей не истекают.</span><span class="sxs-lookup"><span data-stu-id="2da3b-112">You can also use [AzureAD](/powershell/module/Azuread) cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span>

<span data-ttu-id="2da3b-113">Это руководство применяется к другим поставщикам, таким как Intune и Microsoft 365, которые также используют Azure AD для служб удостоверений и каталогов.</span><span class="sxs-lookup"><span data-stu-id="2da3b-113">This guide applies to other providers, such as Intune and Microsoft 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="2da3b-114">Срок действия пароля — это единственная часть политики, которую можно изменить.</span><span class="sxs-lookup"><span data-stu-id="2da3b-114">Password expiration is the only part of the policy that can be changed.</span></span>

> [!NOTE]
> <span data-ttu-id="2da3b-115">Можно настроить только пароли для учетных записей пользователей, которые не синхронизируются с помощью синхронизации каталогов.</span><span class="sxs-lookup"><span data-stu-id="2da3b-115">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="2da3b-116">Дополнительные сведения о синхронизации каталогов см. в Подключение [AD с Azure AD.](/azure/active-directory/connect/active-directory-aadconnect)</span><span class="sxs-lookup"><span data-stu-id="2da3b-116">For more information about directory synchronization, see [Connect AD with Azure AD](/azure/active-directory/connect/active-directory-aadconnect).</span></span>

## <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="2da3b-117">Проверка политики истечения срока действия пароля</span><span class="sxs-lookup"><span data-stu-id="2da3b-117">How to check the expiration policy for a password</span></span>

<span data-ttu-id="2da3b-118">Дополнительные сведения о команде Get-AzureADUser в модуле AzureAD см. в справочной статье [Get-AzureADUser.](/powershell/module/Azuread/Get-AzureADUser)</span><span class="sxs-lookup"><span data-stu-id="2da3b-118">For more information about the Get-AzureADUser command in the AzureAD module, see the reference article [Get-AzureADUser](/powershell/module/Azuread/Get-AzureADUser).</span></span>

<span data-ttu-id="2da3b-119">Выполните одну из следующих команд:</span><span class="sxs-lookup"><span data-stu-id="2da3b-119">Run one of the following commands:</span></span>

- <span data-ttu-id="2da3b-120">Чтобы узнать, не установлен ли срок действия пароля одного пользователя, запустите следующий cmdlet с помощью upN (например, *user@contoso.onmicrosoft.com)* или пользовательского ID пользователя, который необходимо проверить:</span><span class="sxs-lookup"><span data-stu-id="2da3b-120">To see if a single user's password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    <span data-ttu-id="2da3b-121">Пример.</span><span class="sxs-lookup"><span data-stu-id="2da3b-121">Example:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

- <span data-ttu-id="2da3b-122">Чтобы параметр **Password никогда не истекал** для всех пользователей, запустите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="2da3b-122">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- <span data-ttu-id="2da3b-123">Чтобы получить отчет всех пользователей с PasswordNeverExpires в Html на рабочем столе текущего пользователя с  **именемReportPasswordNeverExpires.html**</span><span class="sxs-lookup"><span data-stu-id="2da3b-123">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```

- <span data-ttu-id="2da3b-124">Чтобы получить отчет всех пользователей с passwordNeverExpires в CSV на рабочем столе текущего пользователя с именем **ReportPasswordNeverExpires.csv**</span><span class="sxs-lookup"><span data-stu-id="2da3b-124">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>

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

- <span data-ttu-id="2da3b-125">Чтобы пароли всех пользователей организации никогда не истекли, запустите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="2da3b-125">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> <span data-ttu-id="2da3b-126">Учетные записи пользователей, настроенные с `-PasswordPolicies DisablePasswordExpiration` параметром still age на основе `pwdLastSet` атрибута.</span><span class="sxs-lookup"><span data-stu-id="2da3b-126">User accounts configured with the `-PasswordPolicies DisablePasswordExpiration` parameter still age based on the `pwdLastSet` attribute.</span></span> <span data-ttu-id="2da3b-127">В зависимости от атрибута, если срок действия меняется на, все пароли с pwdLastSet старше 90 дней требуют от пользователя изменить их при следующем `pwdLastSet` `-PasswordPolicies None` входе.</span><span class="sxs-lookup"><span data-stu-id="2da3b-127">Based on the `pwdLastSet` attribute, if you change the expiration to `-PasswordPolicies None`, all passwords that have a pwdLastSet older than 90 days require the user to change them the next time they sign in.</span></span> <span data-ttu-id="2da3b-128">Это изменение может повлиять на большое число пользователей.</span><span class="sxs-lookup"><span data-stu-id="2da3b-128">This change can affect a large number of users.</span></span>

### <a name="set-a-password-to-expire"></a><span data-ttu-id="2da3b-129">Установите срок действия пароля</span><span class="sxs-lookup"><span data-stu-id="2da3b-129">Set a password to expire</span></span>

<span data-ttu-id="2da3b-130">Выполните одну из следующих команд:</span><span class="sxs-lookup"><span data-stu-id="2da3b-130">Run one of the following commands:</span></span>

- <span data-ttu-id="2da3b-131">Чтобы установить пароль одного пользователя, чтобы срок действия пароля истек, запустите следующий комдлет с помощью upN или пользовательского ID пользователя:</span><span class="sxs-lookup"><span data-stu-id="2da3b-131">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- <span data-ttu-id="2da3b-132">Чтобы установить пароли всех пользователей в организации, чтобы они истекли, используйте следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="2da3b-132">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

## <a name="related-content"></a><span data-ttu-id="2da3b-133">Связанные материалы</span><span class="sxs-lookup"><span data-stu-id="2da3b-133">Related content</span></span>

<span data-ttu-id="2da3b-134">[Предоставление пользователям прав на самостоятельный сброс пароля](../add-users/let-users-reset-passwords.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="2da3b-134">[Let users reset their own passwords](../add-users/let-users-reset-passwords.md) (article)</span></span>\
<span data-ttu-id="2da3b-135">[Сброс паролей](../add-users/reset-passwords.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="2da3b-135">[Reset passwords](../add-users/reset-passwords.md) (article)</span></span>\
<span data-ttu-id="2da3b-136">[Установите политику истечения пароля для организации](../manage/set-password-expiration-policy.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="2da3b-136">[Set the password expiration policy for your organization](../manage/set-password-expiration-policy.md) (article)</span></span>