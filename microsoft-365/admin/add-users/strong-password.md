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
ms.openlocfilehash: 9f6fd61396d99245ffeabf757d3cb65c5d5cb85e
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646623"
---
# <a name="set-strong-password-requirement-for-users"></a><span data-ttu-id="a65ac-103">Определение требований к надежному паролю для пользователей</span><span class="sxs-lookup"><span data-stu-id="a65ac-103">Set strong password requirement for users</span></span>

<span data-ttu-id="a65ac-104">В этой статье объясняется, как отключить требования к надежному паролю для пользователей.</span><span class="sxs-lookup"><span data-stu-id="a65ac-104">This article explains how to turn off strong password requirements for your users.</span></span> <span data-ttu-id="a65ac-105">Требования к надежному паролю включены по умолчанию в организации Microsoft 365 для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="a65ac-105">Strong password requirements are turned on by default in your Microsoft 365 for business organization.</span></span> <span data-ttu-id="a65ac-106">У вашей организации могут быть требования для отключения надежных паролей.</span><span class="sxs-lookup"><span data-stu-id="a65ac-106">Your organization might have requirements to disable strong passwords.</span></span> <span data-ttu-id="a65ac-107">Чтобы отключить требования к надежному паролю, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="a65ac-107">Follow the steps below to turn off strong password requirements.</span></span> <span data-ttu-id="a65ac-108">Необходимо выполнить эти действия с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a65ac-108">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a65ac-109">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="a65ac-109">Before you begin</span></span>

<span data-ttu-id="a65ac-110">Эта статья предназначена для пользователей, которые управляют политикой паролей для бизнеса, учебного заведения или некоммерческой организации.</span><span class="sxs-lookup"><span data-stu-id="a65ac-110">This article is for people who manage password policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="a65ac-111">Чтобы выполнить эти действия, вам нужно войти с помощью своей учетной записи администратора Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a65ac-111">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="a65ac-112">Что такое учетная запись администратора?</span><span class="sxs-lookup"><span data-stu-id="a65ac-112">What's an admin account?</span></span>](../admin-overview/admin-overview.md) <span data-ttu-id="a65ac-113">Для выполнения этих действий необходимо быть [глобальным администратором или администратором паролей](about-admin-roles.md) .</span><span class="sxs-lookup"><span data-stu-id="a65ac-113">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="a65ac-114">Кроме того, необходимо подключиться к Microsoft 365 с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a65ac-114">You must also connect to Microsoft 365 with PowerShell.</span></span>

## <a name="set-strong-passwords"></a><span data-ttu-id="a65ac-115">Установка надежных паролей</span><span class="sxs-lookup"><span data-stu-id="a65ac-115">Set strong passwords</span></span>

1. <span data-ttu-id="a65ac-116">[Подключитесь к Microsoft 365 с помощью PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="a65ac-116">[Connect to Microsoft 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

2. <span data-ttu-id="a65ac-117">С помощью PowerShell можно отключить требования к надежному паролю для всех пользователей с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="a65ac-117">Using PowerShell, you can turn off strong password requirements for all users with the following command:</span></span>

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn of strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> <span data-ttu-id="a65ac-118">Параметр userPrincipalName должен быть в формате для входа в Интернет, где за именем пользователя следуют знак "@" и доменное имя.</span><span class="sxs-lookup"><span data-stu-id="a65ac-118">The userPrincipalName must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name.</span></span> <span data-ttu-id="a65ac-119">Пример: user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="a65ac-119">For example: user@contoso.com.</span></span>

## <a name="related-content"></a><span data-ttu-id="a65ac-120">Связанные материалы</span><span class="sxs-lookup"><span data-stu-id="a65ac-120">Related content</span></span>

[<span data-ttu-id="a65ac-121">Подключение к Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="a65ac-121">How to connect to Microsoft 365 with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[<span data-ttu-id="a65ac-122">Дополнительные сведения о командах MsolUser PowerShell</span><span class="sxs-lookup"><span data-stu-id="a65ac-122">More information on PowerShell MsolUser commands</span></span>](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[<span data-ttu-id="a65ac-123">Дополнительные сведения о политике паролей</span><span class="sxs-lookup"><span data-stu-id="a65ac-123">More information on password policy</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)