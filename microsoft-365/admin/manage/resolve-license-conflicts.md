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
description: Узнайте, как устранять конфликты лицензий с подпиской на Microsoft 365 для бизнеса.
ms.openlocfilehash: a7f0b5cbca98a0550954e322c6fbe51d93627ee4
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645087"
---
# <a name="resolve-license-conflicts"></a>Устранение конфликтов лицензий

::: moniker range="o365-21vianet"

> [!NOTE]
> Изменяется Центр администрирования. Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Мы рекомендуем приобрести лицензии, необходимые для подписки, прежде чем создавать новых пользователей. Таким образом, при создании учетных записей пользователей лицензия может быть назначена новым пользователям. Если вы уже назначили все лицензии пользователям, но у них истек срок действия, или если вы попытаетесь удалить лицензию, которая уже назначена пользователю, возникнут конфликты лицензий. Дополнительные сведения см. [в статье Удаление лицензий из подписки](../../commerce/licenses/remove-licenses-from-subscription.md).
  
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

2. Чтобы узнать, нет ли конфликтов, проверьте столбец **Состояние**. При возникновении конфликта отображается предупреждающее сообщение о том, что одному или нескольким пользователям требуется действительная лицензия.

    > [!NOTE]
    > Если конфликты отсутствуют, столбец **Состояние** не отображается.

## <a name="how-do-i-resolve-license-conflicts"></a>Устранение конфликтов лицензий

Конфликты лицензий можно устранить, [приобретая дополнительные лицензии](../../commerce/licenses/buy-licenses.md) или [удалив лицензии от пользователей, которым они больше не нужны](remove-licenses-from-users.md). Вы также можете [удалить учетную запись пользователя, чтобы высвободить лицензию](../add-users/delete-a-user.md).
  
## <a name="related-articles"></a>Статьи по теме

[Назначение лицензий пользователям](assign-licenses-to-users.md)
  
[Удаление лицензий у пользователей](remove-licenses-from-users.md)
