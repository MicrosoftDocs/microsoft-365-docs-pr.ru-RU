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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466
description: Сведения о том, как задать срок действия отдельных паролей для отдельных пользователей с помощью Windows PowerShell.
ms.openlocfilehash: f85eb2d3aaf5b19779ea8f293e2cbdc28c1535aa
ms.sourcegitcommit: 5c16d270c7651c2080a5043d273d979a6fcc75c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2020
ms.locfileid: "46804212"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="33ec2-103">Установка бессрочных пользовательских паролей</span><span class="sxs-lookup"><span data-stu-id="33ec2-103">Set an individual user's password to never expire</span></span>

## <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="33ec2-104">Установка политики срока действия паролей в организации</span><span class="sxs-lookup"><span data-stu-id="33ec2-104">Set the password expiration policy for your organization</span></span>

1. <span data-ttu-id="33ec2-105">В центре администрирования откройте страницу " **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Параметры</a> настройки".</span><span class="sxs-lookup"><span data-stu-id="33ec2-105">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Settings</a> page.</span></span>
2. <span data-ttu-id="33ec2-106">В верхней части страницы Параметры выберите **безопасность & конфиденциальность**.</span><span class="sxs-lookup"><span data-stu-id="33ec2-106">At the top of the Settings page select **Security & Privacy**.</span></span>
3. <span data-ttu-id="33ec2-107">Выберите **Политика срока действия паролей**</span><span class="sxs-lookup"><span data-stu-id="33ec2-107">Select **Password expiration policy**.</span></span> 
4. <span data-ttu-id="33ec2-108">Если срок действия паролей не ограничен, установите флажок **установить срок действия паролей пользователей через некоторое количество дней**.</span><span class="sxs-lookup"><span data-stu-id="33ec2-108">If passwords are set to never expire, click the check box next to **Set user passwords to expire after a number of days**.</span></span> <span data-ttu-id="33ec2-109">Вы получите возможность указать количество дней до истечения срока действия паролей.</span><span class="sxs-lookup"><span data-stu-id="33ec2-109">You'll get the option to specify the number of days until passwords expire.</span></span>

## <a name="set-the-password-expiration-policy-for-individual-users"></a><span data-ttu-id="33ec2-110">Настройка политики истечения срока действия паролей для отдельных пользователей</span><span class="sxs-lookup"><span data-stu-id="33ec2-110">Set the password expiration policy for individual users</span></span>

<span data-ttu-id="33ec2-111">Глобальный администратор облачной службы Майкрософт может использовать [PowerShell Azure Active Directory для Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) , чтобы задать неограниченный срок действия паролей для определенных пользователей.</span><span class="sxs-lookup"><span data-stu-id="33ec2-111">A global admin for a Microsoft cloud service can use the [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) to set passwords not to expire for specific users.</span></span> <span data-ttu-id="33ec2-112">Кроме того, вы можете использовать командлеты [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) , чтобы удалить конфигурацию с неограниченным сроком действия или убедиться, что срок действия паролей пользователей неограничен.</span><span class="sxs-lookup"><span data-stu-id="33ec2-112">You can also use [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span>

<span data-ttu-id="33ec2-113">Это руководство относится к другим поставщикам, таким как Intune и Microsoft 365, которые также основываются на Azure AD для идентификации и служб каталогов.</span><span class="sxs-lookup"><span data-stu-id="33ec2-113">This guide applies to other providers, such as Intune and Microsoft 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="33ec2-114">Срок действия пароля является единственной частью политики, которую можно изменить.</span><span class="sxs-lookup"><span data-stu-id="33ec2-114">Password expiration is the only part of the policy that can be changed.</span></span>

<span data-ttu-id="33ec2-115">Для получения дополнительных сведений об Azure AD PowerShell для Graph, обратитесь [к статье Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0).</span><span class="sxs-lookup"><span data-stu-id="33ec2-115">For more information about Azure AD PowerShell for Graph, see [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0).</span></span>

> [!NOTE]
> <span data-ttu-id="33ec2-116">Срок действия только паролей для учетных записей пользователей, которые не синхронизируются с помощью синхронизации службы каталогов, может быть запрещен.</span><span class="sxs-lookup"><span data-stu-id="33ec2-116">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="33ec2-117">Дополнительные сведения о синхронизации службы каталогов можно найти [в статье Connect AD with Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="33ec2-117">For more information about directory synchronization, see [Connect AD with Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>

### <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="33ec2-118">Проверка политики истечения срока действия для пароля</span><span class="sxs-lookup"><span data-stu-id="33ec2-118">How to check the expiration policy for a password</span></span>

<span data-ttu-id="33ec2-119">Дополнительные сведения о команде Get – AzureADUser в модуле AzureAD можно найти в справочной статье [Get/AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span><span class="sxs-lookup"><span data-stu-id="33ec2-119">For more information about the Get-AzureADUser command in the AzureAD module, see the reference article [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span></span>

<span data-ttu-id="33ec2-120">Выполните одну из следующих команд:</span><span class="sxs-lookup"><span data-stu-id="33ec2-120">Run one of the following commands:</span></span>

- <span data-ttu-id="33ec2-121">Чтобы убедиться, что срок действия пароля одного пользователя не ограничен, выполните следующий командлет с помощью имени участника-пользователя (например, *user@contoso.onmicrosoft.com*) или идентификатора пользователя, которого вы хотите проверить:</span><span class="sxs-lookup"><span data-stu-id="33ec2-121">To see if a single user's password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    <span data-ttu-id="33ec2-122">Пример.</span><span class="sxs-lookup"><span data-stu-id="33ec2-122">Example:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- <span data-ttu-id="33ec2-123">Чтобы увидеть, что параметр **Password не истечет срок действия** для всех пользователей, выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="33ec2-123">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- <span data-ttu-id="33ec2-124">Получение отчета обо всех пользователях с PasswordNeverExpires в HTML-коде на рабочем столе текущего пользователя с именем  **ReportPasswordNeverExpires.html**</span><span class="sxs-lookup"><span data-stu-id="33ec2-124">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- <span data-ttu-id="33ec2-125">Чтобы получить отчет обо всех пользователях с PasswordNeverExpires в CSV на рабочем столе текущего пользователя с именем **ReportPasswordNeverExpires.csv**</span><span class="sxs-lookup"><span data-stu-id="33ec2-125">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv
    ```

### <a name="set-a-password-to-expire"></a><span data-ttu-id="33ec2-126">Установка срока действия пароля</span><span class="sxs-lookup"><span data-stu-id="33ec2-126">Set a password to expire</span></span>

<span data-ttu-id="33ec2-127">Выполните одну из следующих команд:</span><span class="sxs-lookup"><span data-stu-id="33ec2-127">Run one of the following commands:</span></span>

- <span data-ttu-id="33ec2-128">Чтобы задать пароль одного пользователя, чтобы срок действия пароля истек, выполните следующий командлет с помощью имени участника-пользователя или идентификатора пользователя:</span><span class="sxs-lookup"><span data-stu-id="33ec2-128">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- <span data-ttu-id="33ec2-129">Чтобы задать пароли всех пользователей в Организации, истечения срока их действия, используйте следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="33ec2-129">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

### <a name="set-a-password-to-never-expire"></a><span data-ttu-id="33ec2-130">Установка срока действия пароля не ограничена</span><span class="sxs-lookup"><span data-stu-id="33ec2-130">Set a password to never expire</span></span>

<span data-ttu-id="33ec2-131">Выполните одну из следующих команд:</span><span class="sxs-lookup"><span data-stu-id="33ec2-131">Run one of the following commands:</span></span>

- <span data-ttu-id="33ec2-132">Чтобы задать срок действия пароля одного пользователя, выполните следующий командлет с помощью имени участника-пользователя или идентификатора пользователя:</span><span class="sxs-lookup"><span data-stu-id="33ec2-132">To set the password of one user to never expire, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration
    ```

- <span data-ttu-id="33ec2-133">Чтобы запретить срок действия паролей для всех пользователей в Организации, выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="33ec2-133">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> <span data-ttu-id="33ec2-134">Учетные записи пользователей, настроенные с `-PasswordPolicies DisablePasswordExpiration` параметром, по-прежнему возрастются на основе `pwdLastSet` атрибута учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="33ec2-134">User accounts configured with the `-PasswordPolicies DisablePasswordExpiration` parameter still age based on the `pwdLastSet` user account attribute.</span></span> <span data-ttu-id="33ec2-135">Например, если вы настроили пароли пользователей, срок действия которых не истечет, а затем — 90 или более дней, срок действия паролей не истечет.</span><span class="sxs-lookup"><span data-stu-id="33ec2-135">For example, if you set user passwords to never expire and then 90 or more days go by, the passwords still expire.</span></span> <span data-ttu-id="33ec2-136">На основе `pwdLastSet` атрибута учетной записи пользователя для учетных записей пользователей, настроенных с помощью этого `-PasswordPolicies None` параметра, все пароли, имеющие `pwdLastSet` старше 90 дней, должны изменить их при следующем входе в систему. Это изменение может повлиять на большое количество пользователей.</span><span class="sxs-lookup"><span data-stu-id="33ec2-136">Based on the `pwdLastSet` user account attribute, for user accounts configured with the `-PasswordPolicies None` parameter, all passwords that have a `pwdLastSet` older than 90 days require the user to change them the next time they sign in.This change can affect a large number of users.</span></span>
