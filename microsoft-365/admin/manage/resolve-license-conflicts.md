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
description: Узнайте, как разрешить конфликт лицензий с microsoft 365 для бизнес-подписки.
ms.openlocfilehash: e2b5daa71164b41825282bd5652549347b8307c1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915186"
---
# <a name="resolve-license-conflicts"></a>Устранение конфликтов лицензий

::: moniker range="o365-21vianet"

> [!NOTE]
> Изменяется Центр администрирования. Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).

::: moniker-end

Перед созданием новых пользователей рекомендуется приобрести лицензии, необходимые для подписки. Таким образом, по мере создания учетных записей пользователей лицензия может быть назначена новым пользователям. Если все лицензии уже назначены пользователям, но срок действия некоторых лицензий истек, или вы пытаетесь удалить лицензию, которая уже назначена пользователю, у вас будут конфликты лицензий. Дополнительные сведения см. в [журнале Remove licenses from your subscription.](../../commerce/licenses/buy-licenses.md)
  
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

2. Чтобы узнать, нет ли конфликтов, проверьте столбец **Состояние**. Если произошел конфликт, вы увидите предупреждающий сигнал, в нем говорится, что одному или более пользователям нужна действительная лицензия.

    > [!NOTE]
    > Если конфликты отсутствуют, столбец **Состояние** не отображается.

## <a name="how-do-i-resolve-license-conflicts"></a>Устранение конфликтов лицензий

Конфликты лицензий можно разрешить путем [покупки](../../commerce/licenses/buy-licenses.md) дополнительных лицензий или удаления лицензий у [пользователей, которым они](remove-licenses-from-users.md)больше не нужны. Вы также можете [удалить учетную запись пользователя, чтобы высвободить лицензию](../add-users/delete-a-user.md).
  
## <a name="related-articles"></a>Статьи по теме

[Назначение лицензий пользователям](assign-licenses-to-users.md)
  
[Удаление лицензий у пользователей](remove-licenses-from-users.md)