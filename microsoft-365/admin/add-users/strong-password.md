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
ms.openlocfilehash: 1230ff4b4235ac5acbc28aa823506dfa5af26c2d
ms.sourcegitcommit: 3165329d1fb5a7fd866ff287bea3b6354ea2be18
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48581028"
---
# <a name="set-strong-password-requirement-for-users"></a>Определение требований к надежному паролю для пользователей

В этой статье объясняется, как задать требования к надежному паролю для пользователей. Необходимо выполнить эти действия с помощью PowerShell.

## <a name="before-you-begin"></a>Прежде чем начать

Эта статья предназначена для пользователей, которые управляют политикой паролей для бизнеса, учебного заведения или некоммерческой организации. Чтобы выполнить эти действия, вам нужно войти с помощью своей учетной записи администратора Microsoft 365. [Что такое учетная запись администратора?](../admin-overview/admin-overview.md) Для выполнения этих действий необходимо быть [глобальным администратором или администратором паролей](about-admin-roles.md) .

Кроме того, необходимо подключиться к Microsoft 365 с помощью PowerShell.

## <a name="set-strong-passwords"></a>Установка надежных паролей

1. [Подключитесь к Microsoft 365 с помощью PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

2. С помощью PowerShell можно отключить надежные пароли для определенных пользователей с помощью этой команды:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> Параметр userPrincipalName должен быть в формате для входа в Интернет, где за именем пользователя следуют знак "@" и доменное имя. Пример: user@contoso.com.

## <a name="related-content"></a>Связанные материалы

[Подключение к Microsoft 365 с помощью PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[Дополнительные сведения о командах MsolUser PowerShell](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[Дополнительные сведения о политике паролей](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)