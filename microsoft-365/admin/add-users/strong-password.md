---
title: Отключение требований к надежных паролям для пользователей
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
description: Узнайте, как настроить надежные требования к паролям для пользователей с помощью Windows PowerShell.
ms.openlocfilehash: f9a0b76d024cc18552657144e4ccf8de8a72f0d9
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2020
ms.locfileid: "48655739"
---
# <a name="turn-off-strong-password-requirements-for-users"></a>Отключение требований к надежных паролям для пользователей

В этой статье объясняется, как отключить требования к надежных паролям для пользователей. В вашей организации Microsoft 365 для бизнеса по умолчанию отключены требования к надежных паролям. В организации могут быть требования к отключению надежных паролей. Чтобы отключить требования к надежных паролям, выполните следующие действия. Эти действия необходимо выполнить с помощью PowerShell.

## <a name="before-you-begin"></a>Прежде чем начать

Эта статья для пользователей, которые управляют политикой паролей для бизнеса, учебного заведения или некоммерческой организации. Чтобы выполнить эти действия, вам нужно войти с помощью своей учетной записи администратора Microsoft 365. [Что такое учетная запись администратора?](../admin-overview/admin-overview.md) Для выполнения этих действий [необходимо быть](about-admin-roles.md) глобальным администратором или администратором паролей.

Вам также необходимо подключиться к Microsoft 365 с помощью PowerShell.

## <a name="set-strong-passwords"></a>Настройка надежных паролей

1. [Подключись к Microsoft 365 с помощью PowerShell.](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

2. С помощью PowerShell можно отключить требования к надежных паролям для всех пользователей с помощью следующей команды:

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn of strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> Параметр userPrincipalName должен иметь формат для доступа в Интернет, в котором за именем пользователя следует знак @и доменное имя. Например: user@contoso.com.

## <a name="related-content"></a>Связанные материалы

[Подключение к Microsoft 365 с помощью PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[Дополнительные сведения о командах PowerShell MsolUser](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[Дополнительные сведения о политике паролей](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)