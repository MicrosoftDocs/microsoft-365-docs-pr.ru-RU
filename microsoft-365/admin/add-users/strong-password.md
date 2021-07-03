---
title: Отключение требований к паролям для пользователей
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
description: Узнайте, как установить надежные требования к паролям для пользователей с помощью Windows PowerShell.
ms.openlocfilehash: 87ba9e0323c379d8c2589dbb82c38c531dd9d047
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286271"
---
# <a name="turn-off-strong-password-requirements-for-users"></a><span data-ttu-id="7d89e-103">Отключение требований к паролям для пользователей</span><span class="sxs-lookup"><span data-stu-id="7d89e-103">Turn off strong password requirements for users</span></span>

<span data-ttu-id="7d89e-104">В этой статье рассказывается о том, как отключить надежные требования к паролям для пользователей.</span><span class="sxs-lookup"><span data-stu-id="7d89e-104">This article explains how to turn off strong password requirements for your users.</span></span> <span data-ttu-id="7d89e-105">В вашей Microsoft 365 для организации бизнеса по умолчанию включаются надежные требования к паролям.</span><span class="sxs-lookup"><span data-stu-id="7d89e-105">Strong password requirements are turned on by default in your Microsoft 365 for business organization.</span></span> <span data-ttu-id="7d89e-106">У организации могут быть требования к отключению надежных паролей.</span><span class="sxs-lookup"><span data-stu-id="7d89e-106">Your organization might have requirements to disable strong passwords.</span></span> <span data-ttu-id="7d89e-107">Выполните ниже шаги, чтобы отключить требования к паролям.</span><span class="sxs-lookup"><span data-stu-id="7d89e-107">Follow the steps below to turn off strong password requirements.</span></span> <span data-ttu-id="7d89e-108">Эти действия необходимо выполнить с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7d89e-108">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="7d89e-109">Подготовка</span><span class="sxs-lookup"><span data-stu-id="7d89e-109">Before you begin</span></span>

<span data-ttu-id="7d89e-110">Эта статья для людей, которые управляют политикой паролей для бизнеса, школы или некоммерческой организации.</span><span class="sxs-lookup"><span data-stu-id="7d89e-110">This article is for people who manage password policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="7d89e-111">Чтобы выполнить эти действия, вам нужно войти с помощью своей учетной записи администратора Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7d89e-111">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="7d89e-112">Что такое учетная запись администратора?</span><span class="sxs-lookup"><span data-stu-id="7d89e-112">What's an admin account?</span></span>](/microsoft-365/business-video/admin-center-overview) <span data-ttu-id="7d89e-113">Для выполнения этих [действий](about-admin-roles.md) необходимо быть глобальным администратором или администратором паролей.</span><span class="sxs-lookup"><span data-stu-id="7d89e-113">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="7d89e-114">Также необходимо подключиться к Microsoft 365 PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7d89e-114">You must also connect to Microsoft 365 with PowerShell.</span></span>

## <a name="set-strong-passwords"></a><span data-ttu-id="7d89e-115">Настройка надежных паролей</span><span class="sxs-lookup"><span data-stu-id="7d89e-115">Set strong passwords</span></span>

1. <span data-ttu-id="7d89e-116">[Подключение Microsoft 365 PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="7d89e-116">[Connect to Microsoft 365 with PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

2. <span data-ttu-id="7d89e-117">С помощью PowerShell можно отключить надежные требования к паролям для всех пользователей со следующей командой:</span><span class="sxs-lookup"><span data-stu-id="7d89e-117">Using PowerShell, you can turn off strong password requirements for all users with the following command:</span></span>

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn of strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> <span data-ttu-id="7d89e-118">UserPrincipalName должен быть в формате вход в Интернет, где за именем пользователя следует знак (@) и доменное имя.</span><span class="sxs-lookup"><span data-stu-id="7d89e-118">The userPrincipalName must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name.</span></span> <span data-ttu-id="7d89e-119">Например: user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="7d89e-119">For example: user@contoso.com.</span></span>

## <a name="related-content"></a><span data-ttu-id="7d89e-120">Связанные материалы</span><span class="sxs-lookup"><span data-stu-id="7d89e-120">Related content</span></span>

[<span data-ttu-id="7d89e-121">Подключение к Microsoft 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="7d89e-121">How to connect to Microsoft 365 with PowerShell</span></span>](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[<span data-ttu-id="7d89e-122">Дополнительные сведения о командах PowerShell MsolUser</span><span class="sxs-lookup"><span data-stu-id="7d89e-122">More information on PowerShell MsolUser commands</span></span>](/powershell/azure/active-directory/install-adv2)

[<span data-ttu-id="7d89e-123">Дополнительные сведения о политике паролей</span><span class="sxs-lookup"><span data-stu-id="7d89e-123">More information on password policy</span></span>](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)
