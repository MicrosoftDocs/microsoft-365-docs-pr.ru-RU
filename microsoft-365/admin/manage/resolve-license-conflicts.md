---
title: Устранение конфликтов лицензий
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 796f7eda-b1f8-479a-adee-bd9226ca47ec
description: Узнайте, как устранить конфликты лицензий с подпиской на Microsoft 365 для бизнеса.
ms.openlocfilehash: 284a6b169c02314dd2bbd0e13c10c081cb50f58d
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114457"
---
# <a name="resolve-license-conflicts"></a>Устранение конфликтов лицензий

::: moniker range="o365-21vianet"

> [!NOTE]
> Изменяется Центр администрирования. Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

Рекомендуем приобрести лицензии, необходимые для подписки, прежде чем создавать новых пользователей. Таким образом, лицензия может быть назначена новым пользователям по мере создания учетных записей пользователей. Если вы уже написили пользователям все лицензии, но срок действия некоторых лицензий истек или вы пытаетесь удалить лицензию, которая уже назначена пользователю, у вас будут конфликты лицензий. Дополнительные сведения см. в [теме "Удаление лицензий из подписки".](../../commerce/licenses/remove-licenses-from-subscription.md)
  
## <a name="how-do-i-view-license-conflicts"></a>Просмотр конфликтов лицензий

::: moniker range="o365-worldwide"

1. В Центре администрирования выберите **Выставление счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Лицензии</a>.

::: moniker-end

::: moniker range="o365-germany"

1. В Центре администрирования выберите **Выставление счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Лицензии</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. В Центре администрирования выберите **Выставление счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Лицензии</a>.

::: moniker-end

2. Чтобы узнать, нет ли конфликтов, проверьте столбец **Состояние**. В случае конфликта вы увидите предупреждение о том, что одному или несколько пользователей нужна действительная лицензия.

    > [!NOTE]
    > Если конфликты отсутствуют, столбец **Состояние** не отображается.

## <a name="how-do-i-resolve-license-conflicts"></a>Устранение конфликтов лицензий

Вы можете устранить конфликты лицензий, [приобретая](../../commerce/licenses/buy-licenses.md) дополнительные лицензии или удаляя лицензии у пользователей, [которым они больше не нужны.](remove-licenses-from-users.md) Вы также можете [удалить учетную запись пользователя, чтобы высвободить лицензию](../add-users/delete-a-user.md).
  
## <a name="related-articles"></a>Статьи по теме

[Назначение лицензий пользователям](assign-licenses-to-users.md)
  
[Удаление лицензий у пользователей](remove-licenses-from-users.md)
