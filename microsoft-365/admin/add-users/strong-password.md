---
title: Определение требований к надежному паролю для пользователей
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
description: Узнайте, как задать требования к надежному паролю для пользователей с помощью Windows PowerShell.
ms.openlocfilehash: 1634e2f0de2cdd2cac5e1928adbef54457e50716
ms.sourcegitcommit: e17fd18b01d70e6428263c20cbce4b92e2a97765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/20/2020
ms.locfileid: "48626147"
---
# <a name="set-strong-password-requirement-for-users"></a><span data-ttu-id="3be24-103">Определение требований к надежному паролю для пользователей</span><span class="sxs-lookup"><span data-stu-id="3be24-103">Set strong password requirement for users</span></span>

<span data-ttu-id="3be24-104">В этой статье объясняется, как задать требования к надежному паролю для пользователей.</span><span class="sxs-lookup"><span data-stu-id="3be24-104">This article explains how to set strong password requirements for your users.</span></span> <span data-ttu-id="3be24-105">Необходимо выполнить эти действия с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3be24-105">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="3be24-106">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="3be24-106">Before you begin</span></span>

<span data-ttu-id="3be24-107">Эта статья предназначена для пользователей, которые управляют политикой паролей для бизнеса, учебного заведения или некоммерческой организации.</span><span class="sxs-lookup"><span data-stu-id="3be24-107">This article is for people who manage password policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="3be24-108">Чтобы выполнить эти действия, вам нужно войти с помощью своей учетной записи администратора Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3be24-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="3be24-109">[Что такое учетная запись администратора?](../admin-overview/admin-overview.md)</span><span class="sxs-lookup"><span data-stu-id="3be24-109">[What's an admin account?](../admin-overview/admin-overview.md).</span></span> <span data-ttu-id="3be24-110">Для выполнения этих действий необходимо быть [глобальным администратором или администратором паролей](about-admin-roles.md) .</span><span class="sxs-lookup"><span data-stu-id="3be24-110">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="3be24-111">Кроме того, необходимо подключиться к Microsoft 365 с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3be24-111">You must also connect to Microsoft 365 with PowerShell.</span></span>

## <a name="set-strong-passwords"></a><span data-ttu-id="3be24-112">Установка надежных паролей</span><span class="sxs-lookup"><span data-stu-id="3be24-112">Set strong passwords</span></span>

1. <span data-ttu-id="3be24-113">[Подключитесь к Microsoft 365 с помощью PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="3be24-113">[Connect to Microsoft 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

2. <span data-ttu-id="3be24-114">С помощью PowerShell вы можете включить требования к надежному паролю для всех пользователей, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3be24-114">Using PowerShell, you can turn on strong password requirements for all users with the following command:</span></span>

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $true

3. You can turn on strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $true
    ```

> [!NOTE]
> <span data-ttu-id="3be24-115">Параметр userPrincipalName должен быть в формате для входа в Интернет, где за именем пользователя следуют знак "@" и доменное имя.</span><span class="sxs-lookup"><span data-stu-id="3be24-115">The userPrincipalName must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name.</span></span> <span data-ttu-id="3be24-116">Пример: user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3be24-116">For example: user@contoso.com.</span></span>

## <a name="related-content"></a><span data-ttu-id="3be24-117">Связанные материалы</span><span class="sxs-lookup"><span data-stu-id="3be24-117">Related content</span></span>

[<span data-ttu-id="3be24-118">Подключение к Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="3be24-118">How to connect to Microsoft 365 with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[<span data-ttu-id="3be24-119">Дополнительные сведения о командах MsolUser PowerShell</span><span class="sxs-lookup"><span data-stu-id="3be24-119">More information on PowerShell MsolUser commands</span></span>](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[<span data-ttu-id="3be24-120">Дополнительные сведения о политике паролей</span><span class="sxs-lookup"><span data-stu-id="3be24-120">More information on password policy</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)