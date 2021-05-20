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
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="e024a-103">Установка бессрочных пользовательских паролей</span><span class="sxs-lookup"><span data-stu-id="e024a-103">Set an individual user's password to never expire</span></span>

<span data-ttu-id="e024a-104">В этой статье объясняется, как установить пароль для отдельного пользователя, чтобы не истекать.</span><span class="sxs-lookup"><span data-stu-id="e024a-104">This article explains how to set a password for an individual user to not expire.</span></span> <span data-ttu-id="e024a-105">Вы должны выполнить эти шаги с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e024a-105">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="e024a-106">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="e024a-106">Before you begin</span></span>

<span data-ttu-id="e024a-107">Эта статья адресована тем, кто устанавливает политику срока действия паролей в компании, учебном заведении или некоммерческой организации.</span><span class="sxs-lookup"><span data-stu-id="e024a-107">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="e024a-108">Чтобы выполнить эти действия, вам нужно войти с помощью своей учетной записи администратора Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e024a-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="e024a-109">[Что такое учетная запись администратора?](../../business-video/admin-center-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e024a-109">[What's an admin account?](../../business-video/admin-center-overview.md).</span></span> 

<span data-ttu-id="e024a-110">Вы должны быть глобальным [администратором или администратором паролей](about-admin-roles.md) для выполнения этих шагов.</span><span class="sxs-lookup"><span data-stu-id="e024a-110">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="e024a-111">Глобальный администратор облачного сервиса Майкрософт может использовать [Azure Active Directory PowerShell для Graph](/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) для настройки паролей, срок действия которых не истекает для конкретных пользователей.</span><span class="sxs-lookup"><span data-stu-id="e024a-111">A global admin for a Microsoft cloud service can use the [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) to set passwords not to expire for specific users.</span></span> <span data-ttu-id="e024a-112">Вы также можете использовать [cmdlets AzureAD](/powershell/module/Azuread) для удаления никогда не истекать конфигурации или посмотреть, какие пароли пользователей установлены никогда не истекает.</span><span class="sxs-lookup"><span data-stu-id="e024a-112">You can also use [AzureAD](/powershell/module/Azuread) cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span>

<span data-ttu-id="e024a-113">Это руководство распространяется на других поставщиков, таких как Intune и Microsoft 365, которые также полагаются на Azure AD для служб идентификации и каталогов.</span><span class="sxs-lookup"><span data-stu-id="e024a-113">This guide applies to other providers, such as Intune and Microsoft 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="e024a-114">Срок действия пароля является единственной частью политики, которая может быть изменена.</span><span class="sxs-lookup"><span data-stu-id="e024a-114">Password expiration is the only part of the policy that can be changed.</span></span>

> [!NOTE]
> <span data-ttu-id="e024a-115">Только пароли для учетных записей пользователей, которые не синхронизированы с помощью синхронизации каталога, могут быть настроены, чтобы не истекать.</span><span class="sxs-lookup"><span data-stu-id="e024a-115">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="e024a-116">Для получения дополнительной информации о синхронизации каталогов [см. Подключение нашей эры с Azure AD](/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="e024a-116">For more information about directory synchronization, see [Connect AD with Azure AD](/azure/active-directory/connect/active-directory-aadconnect).</span></span>

## <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="e024a-117">Как проверить полис действия пароля</span><span class="sxs-lookup"><span data-stu-id="e024a-117">How to check the expiration policy for a password</span></span>

<span data-ttu-id="e024a-118">Для получения дополнительной информации о Get-AzureADUser команды в модуле [](/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0)AzureAD, см.</span><span class="sxs-lookup"><span data-stu-id="e024a-118">For more information about the Get-AzureADUser command in the AzureAD module, see the reference article [Get-AzureADUser](/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span></span>

<span data-ttu-id="e024a-119">Выполните одну из следующих команд:</span><span class="sxs-lookup"><span data-stu-id="e024a-119">Run one of the following commands:</span></span>

- <span data-ttu-id="e024a-120">Чтобы узнать, никогда не истечет ли срок действия пароля одного пользователя, запустите следующий cmdlet с помощью UPN *(например, user@contoso.onmicrosoft.com*) или идентификатора пользователя, который вы хотите проверить:</span><span class="sxs-lookup"><span data-stu-id="e024a-120">To see if a single user's password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    <span data-ttu-id="e024a-121">Пример.</span><span class="sxs-lookup"><span data-stu-id="e024a-121">Example:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- <span data-ttu-id="e024a-122">Чтобы увидеть, что **срок действия пароля никогда** не истекает для всех пользователей, запустите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e024a-122">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- <span data-ttu-id="e024a-123">Чтобы получить отчет всех пользователей с PasswordNeverExpires в Html на рабочем столе текущего пользователя с  **именемReportPasswordNeverExpires.html**</span><span class="sxs-lookup"><span data-stu-id="e024a-123">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- <span data-ttu-id="e024a-124">Чтобы получить отчет всех пользователей с PasswordNeverExpires в CSV на рабочем столе текущего пользователя с именем **ReportPasswordNeverExpires.csv**</span><span class="sxs-lookup"><span data-stu-id="e024a-124">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>

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

- <span data-ttu-id="e024a-125">Чтобы установить пароли всех пользователей в организации, чтобы никогда не истекать, запустите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e024a-125">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> <span data-ttu-id="e024a-126">Учетные записи пользователей, настроенные с `-PasswordPolicies DisablePasswordExpiration` параметром, все еще стареют на основе `pwdLastSet` атрибута.</span><span class="sxs-lookup"><span data-stu-id="e024a-126">User accounts configured with the `-PasswordPolicies DisablePasswordExpiration` parameter still age based on the `pwdLastSet` attribute.</span></span> <span data-ttu-id="e024a-127">На основании `pwdLastSet` атрибута, если вы измените срок `-PasswordPolicies None` действия, все пароли, которые имеют pwdLastSet старше 90 дней требуют, чтобы пользователь изменил их при следующем встраивом.</span><span class="sxs-lookup"><span data-stu-id="e024a-127">Based on the `pwdLastSet` attribute, if you change the expiration to `-PasswordPolicies None`, all passwords that have a pwdLastSet older than 90 days require the user to change them the next time they sign in.</span></span> <span data-ttu-id="e024a-128">Это изменение может повлиять на большое количество пользователей.</span><span class="sxs-lookup"><span data-stu-id="e024a-128">This change can affect a large number of users.</span></span>

### <a name="set-a-password-to-expire"></a><span data-ttu-id="e024a-129">Установить пароль для истечения срока действия</span><span class="sxs-lookup"><span data-stu-id="e024a-129">Set a password to expire</span></span>

<span data-ttu-id="e024a-130">Выполните одну из следующих команд:</span><span class="sxs-lookup"><span data-stu-id="e024a-130">Run one of the following commands:</span></span>

- <span data-ttu-id="e024a-131">Чтобы установить пароль одного пользователя, чтобы срок действия пароля истек, запустите следующий cmdlet с помощью UPN или идентификатор пользователя пользователя:</span><span class="sxs-lookup"><span data-stu-id="e024a-131">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- <span data-ttu-id="e024a-132">Чтобы установить пароли всех пользователей в организации, чтобы они истекли, используйте следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e024a-132">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

## <a name="related-content"></a><span data-ttu-id="e024a-133">Связанные материалы</span><span class="sxs-lookup"><span data-stu-id="e024a-133">Related content</span></span>

<span data-ttu-id="e024a-134">[Предоставление пользователям прав на самостоятельный сброс пароля](../add-users/let-users-reset-passwords.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="e024a-134">[Let users reset their own passwords](../add-users/let-users-reset-passwords.md) (article)</span></span>

<span data-ttu-id="e024a-135">[Сброс паролей](../add-users/reset-passwords.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="e024a-135">[Reset passwords](../add-users/reset-passwords.md) (article)</span></span>