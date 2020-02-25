---
title: Устранение конфликтов лицензий в Office 365 для бизнеса
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 796f7eda-b1f8-479a-adee-bd9226ca47ec
description: Узнайте, как устранять конфликты лицензий с подпиской на Office 365 для бизнеса.
ms.openlocfilehash: c96f9e38b3799cb8b77f9422c72a7aec9d001eae
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42254882"
---
# <a name="resolve-license-conflicts-in-office-365-for-business"></a>Устранение конфликтов лицензий в Office 365 для бизнеса

Мы рекомендуем приобрести лицензии, необходимые для подписки, прежде чем создавать новых пользователей. Таким образом, при создании учетных записей пользователей лицензия может быть назначена новым пользователям. Если вы уже назначили все лицензии пользователям, но у них истек срок действия, или если вы попытаетесь удалить лицензию, которая уже назначена пользователю, возникнут конфликты лицензий. Дополнительные сведения см. [в статье Удаление лицензий из подписки](../../commerce/licenses/remove-licenses-from-subscription.md).
  
## <a name="how-do-i-view-license-conflicts"></a>Просмотр конфликтов лицензий

1. В центре администрирования перейдите на страницу <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">лицензии</a> **выставления счетов** \> .

    Если вы используете Office 365 Германии, перейдите на страницу " <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">лицензии</a> ".

    Если вы используете Office 365 под управлением 21Vianet, перейдите на страницу " <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">лицензии</a> ".

2. Чтобы узнать, нет ли конфликтов, проверьте столбец **Состояние**. При возникновении конфликта отображается предупреждающее сообщение о том, что одному или нескольким пользователям требуется действительная лицензия.

    > [!NOTE]
    > Если конфликты отсутствуют, столбец **Состояние** не отображается.

## <a name="how-do-i-resolve-license-conflicts"></a>Устранение конфликтов лицензий

Конфликты лицензий можно устранить, [приобретая дополнительные лицензии](../../commerce/licenses/buy-licenses.md) или [удалив лицензии от пользователей, которым они больше не нужны](remove-licenses-from-users.md). Вы также можете [удалить учетную запись пользователя, чтобы высвободить лицензию](../add-users/delete-a-user.md).
  
## <a name="related-articles"></a>Статьи по теме 

[Назначение лицензий пользователям](assign-licenses-to-users.md)
  
[Удаление лицензий у пользователей](remove-licenses-from-users.md)