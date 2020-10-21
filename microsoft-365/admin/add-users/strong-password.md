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
# <a name="set-strong-password-requirement-for-users"></a>Определение требований к надежному паролю для пользователей

В этой статье объясняется, как отключить требования к надежному паролю для пользователей. Требования к надежному паролю включены по умолчанию в организации Microsoft 365 для бизнеса. У вашей организации могут быть требования для отключения надежных паролей. Чтобы отключить требования к надежному паролю, выполните указанные ниже действия. Необходимо выполнить эти действия с помощью PowerShell.

## <a name="before-you-begin"></a>Прежде чем начать

Эта статья предназначена для пользователей, которые управляют политикой паролей для бизнеса, учебного заведения или некоммерческой организации. Чтобы выполнить эти действия, вам нужно войти с помощью своей учетной записи администратора Microsoft 365. [Что такое учетная запись администратора?](../admin-overview/admin-overview.md) Для выполнения этих действий необходимо быть [глобальным администратором или администратором паролей](about-admin-roles.md) .

Кроме того, необходимо подключиться к Microsoft 365 с помощью PowerShell.

## <a name="set-strong-passwords"></a>Установка надежных паролей

1. [Подключитесь к Microsoft 365 с помощью PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

2. С помощью PowerShell можно отключить требования к надежному паролю для всех пользователей с помощью следующей команды:

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn of strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> Параметр userPrincipalName должен быть в формате для входа в Интернет, где за именем пользователя следуют знак "@" и доменное имя. Пример: user@contoso.com.

## <a name="related-content"></a>Связанные материалы

[Подключение к Microsoft 365 с помощью PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[Дополнительные сведения о командах MsolUser PowerShell](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[Дополнительные сведения о политике паролей](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)