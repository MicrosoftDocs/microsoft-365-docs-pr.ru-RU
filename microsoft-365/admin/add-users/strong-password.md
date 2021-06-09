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
ms.openlocfilehash: 898eaf30d813e883e88c3ccc8ff500d72ae72854
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840662"
---
# <a name="turn-off-strong-password-requirements-for-users"></a>Отключение требований к паролям для пользователей

В этой статье рассказывается о том, как отключить надежные требования к паролям для пользователей. В вашей Microsoft 365 для организации бизнеса по умолчанию включаются надежные требования к паролям. У организации могут быть требования к отключению надежных паролей. Выполните ниже шаги, чтобы отключить требования к паролям. Эти действия необходимо выполнить с помощью PowerShell.

## <a name="before-you-begin"></a>Прежде чем начать

Эта статья для людей, которые управляют политикой паролей для бизнеса, школы или некоммерческой организации. Чтобы выполнить эти действия, вам нужно войти с помощью своей учетной записи администратора Microsoft 365. [Что такое учетная запись администратора?](/microsoft-365/business-video/admin-center-overview) Для выполнения этих [действий](about-admin-roles.md) необходимо быть глобальным администратором или администратором паролей.

Также необходимо подключиться к Microsoft 365 PowerShell.

## <a name="set-strong-passwords"></a>Настройка надежных паролей

1. [Подключение Microsoft 365 PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

2. С помощью PowerShell можно отключить надежные требования к паролям для всех пользователей со следующей командой:

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn of strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> UserPrincipalName должен быть в формате вход в Интернет, где за именем пользователя следует знак (@) и доменное имя. Например: user@contoso.com.

## <a name="related-content"></a>См. также:

[Подключение к Microsoft 365 PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[Дополнительные сведения о командах PowerShell MsolUser](/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[Дополнительные сведения о политике паролей](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)