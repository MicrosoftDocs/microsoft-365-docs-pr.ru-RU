---
title: Удаление домена
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: Узнайте, как удалить старый домен из Microsoft 365 и переместить пользователей и группы в другой домен или отменить подписку.
ms.openlocfilehash: ce75be758edf330226692395dbc6a2c332ed9069
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286253"
---
# <a name="remove-a-domain"></a>Удаление домена

 Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.

Вы удаляете домен, так как хотите добавить его в другой Microsoft 365 подписки? Или вам нужно просто отменить свою подписку? Вы можете [сменить план или подписку](../../commerce/subscriptions/switch-to-a-different-plan.md) либо [отменить подписку](../../commerce/subscriptions/cancel-your-subscription.md).

### <a name="step-1-move-users-to-another-domain"></a>Шаг 1. Перемещение пользователей в другой домен

#### <a name="move-users"></a>Перемещение пользователей

::: moniker range="o365-worldwide"

1. Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Центр администрирования</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Центр администрирования</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Центр администрирования</a>.

::: moniker-end

2. Выбор **пользователей**  >  **Активные пользователи**.

3. Выберите поля рядом с именами всех пользователей, которых вы хотите переместить.

4. В верхней части страницы выберите **домены Change**.

5. В области **Изменить домены** выберите другой домен.

Это нужно сделать и для вашей учетной записи, если она находится в домене, который вы хотите удалить. Чтобы продолжить работу после изменения домена для своей учетной записи, выйдите из службы и снова войдите в нее, используя новый домен.

#### <a name="move-yourself"></a>Перемещение самостоятельно

::: moniker range="o365-worldwide"

1. Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Центр администрирования</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Центр администрирования</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Центр администрирования</a>.

::: moniker-end

2. Перейдите **к активным** \> **пользователям** и выберите учетную запись из списка.

3. На **вкладке Учетная** запись **выберите Управление иным** доменом.

4. В верхней части выберите имя учетной записи, а затем **выберите Sign Out**.

5. Вход с новым доменом и тем же паролем.

Переместить пользователей в другой домен можно также с помощью PowerShell. Дополнительные сведения см. в статье о командлете [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname). Чтобы задать домен по умолчанию, используйте командлет [Set-MsolDomain](/powershell/module/msonline/set-msoldomain).

### <a name="step-2-move-groups-to-another-domain"></a>Шаг 2. Перемещение групп в другой домен

::: moniker range="o365-worldwide"

1. В центре администрирования перейдите на страницу **Группы** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">групп.</a>

::: moniker-end
::: moniker range="o365-germany"

1. В центре <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">администрирования</a>перейдите на страницу **Группы** > **групп.**

::: moniker-end

::: moniker range="o365-21vianet"

1. В центре <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">администрирования</a>перейдите на страницу **Группы** > **групп.**

::: moniker-end

2. Выберите имя группы, а затем на вкладке **General** в соответствии с адресом **электронной почты, Primary**, выберите **Изменить**.

3. Используйте выпадаемый список, чтобы выбрать другой домен.

4. Нажмите кнопку **Сохранить**, а затем — **Закрыть**. Повторите эти шаги для всех групп или списков рассылки, связанных с доменом, который вы хотите удалить.

### <a name="step-3-remove-the-old-domain"></a>Шаг 3. Удаление старого домена

::: moniker range="o365-worldwide"

1. В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).

::: moniker-end

::: moniker range="o365-germany"

1. В центре администрирования перейдите на страницу **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains.</a>

::: moniker-end

::: moniker range="o365-21vianet"

1. В центре администрирования перейдите на страницу **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains.</a>

::: moniker-end

2. На странице **Домены** выберите домен, который необходимо удалить.

3. В правой области выберите **Удалить**.

4. Выполните дополнительные запросы и выберите **Close**.

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a>Время, необходимое для удаления домена

Удаление домена может занять всего 5 минут Microsoft 365 если он не указан во многих местах, таких как группы безопасности, списки рассылки, пользователи и Microsoft 365 группы. Если же домен используется очень широко, на его удаление может потребоваться несколько часов или один день.

Если у вас сотни или тысячи пользователей, используйте PowerShell, чтобы отправить им всем запрос, а затем перенести их в другой домен. В противном случае может оказаться, что нескольких пользователей нет в интерфейсе. В результате вы не сможете удалить домен и не сумеете определить причину. Дополнительные сведения см. в статье о командлете [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname). Чтобы задать домен по умолчанию, используйте командлет [Set-MsolDomain](/powershell/module/msonline/set-msoldomain).

## <a name="still-need-help"></a>Требуется дополнительная помощь?

::: moniker range="o365-worldwide"

> [!NOTE]
> Не удается удалить домен [".onmicrosoft.com"](../setup/domains-faq.yml) из вашей учетной записи. После удаления домена учетные записи пользователей будут возвращаться к адресу ".onmicrosoft.com" в качестве основного SMTP/UserprincipalName.

Не получилось? Возможно, ваш домен необходимо удалить вручную. [Позвоните нем](../../business-video/get-help-support.md), и мы поможем вам это сделать.

::: moniker-end

::: moniker range="o365-germany"

> [!NOTE]
> Вы не можете удалить [домен ".onmicrosoft.de"](../setup/domains-faq.yml) из учетной записи. После удаления домена учетные записи пользователей будут возвращаться к адресу ".onmicrosoft.de" в качестве основного SMTP/UserprincipalName.

Не получилось? Возможно, ваш домен необходимо удалить вручную. [Позвоните нем](../../business-video/get-help-support.md?view=o365-germany&preserve-view=true), и мы поможем вам это сделать.

::: moniker-end

::: moniker range="o365-21vianet"

> [!NOTE]
> Вы не можете удалить [домен ".partner.onmschina.cn"](../setup/domains-faq.yml) из учетной записи. После удаления домена учетные записи пользователей будут возвращаться к адресу ".partner.onmschina.cn" в качестве основного SMTP/UserprincipalName.

Не получилось? Возможно, ваш домен необходимо удалить вручную. [Позвоните нем](../../business-video/get-help-support.md?view=o365-21vianet&preserve-view=true), и мы поможем вам это сделать.

::: moniker-end

## <a name="related-content"></a>См. также:

[Вопросы и ответы о доменах](../setup/domains-faq.yml) (статья)

[Переключиться на другой Microsoft 365 бизнес-плана](../../commerce/subscriptions/switch-to-a-different-plan.md) (статья)

[Отмена подписки](../../commerce/subscriptions/cancel-your-subscription.md) (статья)
