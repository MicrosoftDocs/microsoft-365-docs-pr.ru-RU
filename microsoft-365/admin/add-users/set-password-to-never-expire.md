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
ms.openlocfilehash: 1c44f5c4d5966d70b5fed0b1b99e69b2938c6ddd
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42245666"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="acc06-103">Установка бессрочных пользовательских паролей</span><span class="sxs-lookup"><span data-stu-id="acc06-103">Set an individual user's password to never expire</span></span>

## <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="acc06-104">Установка политики срока действия паролей в организации</span><span class="sxs-lookup"><span data-stu-id="acc06-104">Set the password expiration policy for your organization</span></span>

1. <span data-ttu-id="acc06-105">В центре администрирования перейдите на страницу **Параметры** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">безопасности & конфиденциальность</a> .</span><span class="sxs-lookup"><span data-stu-id="acc06-105">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>
2. <span data-ttu-id="acc06-106">Рядом с полем **Политика паролей** выберите команду **изменить**.</span><span class="sxs-lookup"><span data-stu-id="acc06-106">Next to **Password policy** select **Edit**.</span></span> 
3. <span data-ttu-id="acc06-107">Если срок действия паролей не ограничен, установите переключатель в значение **выкл**.</span><span class="sxs-lookup"><span data-stu-id="acc06-107">If passwords are set to never expire, set the toggle to **Off**.</span></span> <span data-ttu-id="acc06-108">Вы получите возможность указать количество дней до истечения срока действия паролей.</span><span class="sxs-lookup"><span data-stu-id="acc06-108">You'll get the option to specify the number of days until passwords expire.</span></span> 


## <a name="set-the-password-expiration-policy-for-individual-users"></a><span data-ttu-id="acc06-109">Настройка политики истечения срока действия паролей для отдельных пользователей</span><span class="sxs-lookup"><span data-stu-id="acc06-109">Set the password expiration policy for individual users</span></span> 

<span data-ttu-id="acc06-110">Глобальный администратор облачной службы Майкрософт может использовать модуль Microsoft Azure AD для Windows PowerShell, чтобы задать срок действия паролей для определенных пользователей.</span><span class="sxs-lookup"><span data-stu-id="acc06-110">A global admin for a Microsoft cloud service can use the Microsoft Azure AD Module for Windows PowerShell to set passwords not to expire for specific users.</span></span> <span data-ttu-id="acc06-111">Кроме того, вы можете использовать командлеты Windows PowerShell, чтобы удалить конфигурацию, не ограниченную сроком действия, или просмотреть пароли пользователей, срок действия которых не ограничен.</span><span class="sxs-lookup"><span data-stu-id="acc06-111">You can also use Windows PowerShell cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span> 

<span data-ttu-id="acc06-112">Это руководство относится к другим поставщикам, таким как Intune и Office 365, которые также основываются на Azure AD для удостоверений и служб каталогов.</span><span class="sxs-lookup"><span data-stu-id="acc06-112">This guide applies to other providers, such as Intune and Office 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="acc06-113">Срок действия пароля является единственной частью политики, которую можно изменить.</span><span class="sxs-lookup"><span data-stu-id="acc06-113">Password expiration is the only part of the policy that can be changed.</span></span>

> [!NOTE]
> <span data-ttu-id="acc06-114">Срок действия только паролей для учетных записей пользователей, которые не синхронизируются с помощью синхронизации службы каталогов, может быть запрещен.</span><span class="sxs-lookup"><span data-stu-id="acc06-114">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="acc06-115">Дополнительные сведения о синхронизации службы каталогов можно найти [в статье Connect AD with Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="acc06-115">For more information about directory synchronization, see [Connect AD with Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>


### <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="acc06-116">Проверка политики истечения срока действия для пароля</span><span class="sxs-lookup"><span data-stu-id="acc06-116">How to check the expiration policy for a password</span></span>

* <span data-ttu-id="acc06-117">Выполните одну из следующих команд:</span><span class="sxs-lookup"><span data-stu-id="acc06-117">Run one of the following commands:</span></span>

   * <span data-ttu-id="acc06-118">Чтобы убедиться, что срок действия пароля одного пользователя не ограничен, выполните следующий командлет с помощью имени участника-пользователя (например, *user@contoso.onmicrosoft.com*) или идентификатора пользователя, которого вы хотите проверить:</span><span class="sxs-lookup"><span data-stu-id="acc06-118">To see if a single user’s password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>
```
Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
 }
```  
<span data-ttu-id="acc06-119">Пример:</span><span class="sxs-lookup"><span data-stu-id="acc06-119">Example:</span></span>
```
Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
 }
```  

 * <span data-ttu-id="acc06-120">Чтобы увидеть, что параметр **Password не истечет срок действия** для всех пользователей, выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="acc06-120">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span> 
 
```
Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
 }
```  

* <span data-ttu-id="acc06-121">Чтобы получить отчет обо всех пользователях с PasswordNeverExpires в HTML-коде на рабочем столе текущего пользователя с именем **репортпассвордневерекспирес. HTML**</span><span class="sxs-lookup"><span data-stu-id="acc06-121">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>


```
Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
} | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
```  

* <span data-ttu-id="acc06-122">Получение отчета обо всех пользователях с PasswordNeverExpires в CSV на рабочем столе текущего пользователя с именем **репортпассвордневерекспирес. csv**</span><span class="sxs-lookup"><span data-stu-id="acc06-122">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>


```
Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
} | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv
```  


### <a name="set-a-password-to-expire"></a><span data-ttu-id="acc06-123">Установка срока действия пароля</span><span class="sxs-lookup"><span data-stu-id="acc06-123">Set a password to expire</span></span>

<span data-ttu-id="acc06-124">Выполните одну из следующих команд:</span><span class="sxs-lookup"><span data-stu-id="acc06-124">Run one of the following commands:</span></span>

   * <span data-ttu-id="acc06-125">Чтобы задать пароль одного пользователя, чтобы срок действия пароля истек, выполните следующий командлет с помощью имени участника-пользователя или идентификатора пользователя:</span><span class="sxs-lookup"><span data-stu-id="acc06-125">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

```
 Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None

```
   * <span data-ttu-id="acc06-126">Чтобы задать пароли всех пользователей в Организации, истечения срока их действия, используйте следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="acc06-126">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

```
 Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None

```
### <a name="set-a-password-to-never-expire"></a><span data-ttu-id="acc06-127">Установка срока действия пароля не ограничена</span><span class="sxs-lookup"><span data-stu-id="acc06-127">Set a password to never expire</span></span>

<span data-ttu-id="acc06-128">Выполните одну из следующих команд:</span><span class="sxs-lookup"><span data-stu-id="acc06-128">Run one of the following commands:</span></span>

   * <span data-ttu-id="acc06-129">Чтобы задать срок действия пароля одного пользователя, выполните следующий командлет с помощью имени участника-пользователя или идентификатора пользователя:</span><span class="sxs-lookup"><span data-stu-id="acc06-129">To set the password of one user to never expire, run the following cmdlet by using the UPN or the user ID of the user:</span></span> 

```
Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration

```
   * <span data-ttu-id="acc06-130">Чтобы запретить срок действия паролей для всех пользователей в Организации, выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="acc06-130">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span> 

```
Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration

```
   > [!WARNING]
   > <span data-ttu-id="acc06-131">Для `-PasswordPolicies DisablePasswordExpiration` паролей устанавливается срок хранения, `pwdLastSet` основанный на атрибуте.</span><span class="sxs-lookup"><span data-stu-id="acc06-131">Passwords set to `-PasswordPolicies DisablePasswordExpiration` still age based on the `pwdLastSet` attribute.</span></span> <span data-ttu-id="acc06-132">Если вы настроили пароли пользователей, срок действия которых не истечет, а затем — срок действия паролей — 90 + дн.</span><span class="sxs-lookup"><span data-stu-id="acc06-132">If you set the user passwords to never expire and then 90+ days go by, the passwords expire.</span></span> <span data-ttu-id="acc06-133">В зависимости от `pwdLastSet` атрибута, если вы измените срок действия на `-PasswordPolicies None`, то все пароли, имеющие `pwdLastSet` старше 90 дней, должны изменить их при следующем входе в систему.</span><span class="sxs-lookup"><span data-stu-id="acc06-133">Based on the `pwdLastSet` attribute, if you change the expiration to `-PasswordPolicies None`, all passwords that have a `pwdLastSet` older than 90 days require the user to change them the next time they sign in.</span></span> <span data-ttu-id="acc06-134">Это изменение может повлиять на большое количество пользователей.</span><span class="sxs-lookup"><span data-stu-id="acc06-134">This change can affect a large number of users.</span></span> 
