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
description: Узнайте, как удалить старый домен из Microsoft 365 и переместить пользователей и группы в другой домен.
ms.openlocfilehash: cddbb0ef9cf48147e33b93a4a8def15576edfab5
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49655534"
---
# <a name="remove-a-domain"></a>Удаление домена

::: moniker range="o365-21vianet"

> [!NOTE]
> Изменяется Центр администрирования. Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end
  
 Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**. 
  
Вы удаляете домен, потому что хотите добавить его в другой план подписки На Microsoft 365? Или вам нужно просто отменить свою подписку? Вы можете [сменить план или подписку](../../commerce/subscriptions/switch-to-a-different-plan.md) либо [отменить подписку](../../commerce/subscriptions/cancel-your-subscription.md).
  
### <a name="step-1-move-users-to-another-domain"></a>Шаг 1. Перемещение пользователей в другой домен

#### <a name="move-users"></a>Перемещение пользователей

::: moniker range="o365-worldwide"

1. Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Центр администрирования</a>.

2. Выбор  > **активных пользователей пользователей.**

3. Выберите поля рядом с именами всех пользователей, которых нужно переместить.

4. Выберите **дополнительные параметры** **(...**) в верхней части страницы и выберите **"Изменить домены".**

5. В области **"Изменение доменов"** выберите другой домен.

Это нужно сделать и для вашей учетной записи, если она находится в домене, который вы хотите удалить. Чтобы продолжить работу после изменения домена для своей учетной записи, выйдите из службы и снова войдите в нее, используя новый домен.

::: moniker-end

::: moniker range="o365-germany"

1. Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Центр администрирования</a>.  

2. Выберите **"Пользователи** > **активные пользователи"**.

3. Выберите поля рядом с именами всех пользователей, которых нужно переместить.

4. В верхней части страницы выберите **"Дополнительные** > **домены редактирования".**

5. В области **"Изменение доменов"** выберите другой домен.
  
Это нужно сделать и для вашей учетной записи, если она находится в домене, который вы хотите удалить. Чтобы продолжить работу после изменения домена для своей учетной записи, выйдите из службы и снова войдите в нее, используя новый домен.

::: moniker-end

::: moniker range="o365-21vianet"

1. Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Центр администрирования</a>.  

2. Выбор  > **активных пользователей пользователей.**

3. Выберите поля рядом с именами всех пользователей, которых нужно переместить.

4. В верхней части страницы выберите  > **"Дополнительные домены редактирования".**

5. В области **"Изменение доменов"** выберите другой домен.
  
Это нужно сделать и для вашей учетной записи, если она находится в домене, который вы хотите удалить. Чтобы продолжить работу после изменения домена для своей учетной записи, выйдите из службы и снова войдите в нее, используя новый домен.

::: moniker-end

#### <a name="move-yourself"></a>Перемещение себя

::: moniker range="o365-worldwide"

1. Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Центр администрирования</a>.

2. Перейдите **к** \> **"Активные пользователи"** и выберите свою учетную запись в списке.

3. На **вкладке "Учетная** запись" **выберите "Управление именю пользователя",** а затем выберите другой домен.
  
4. В верхней части выберите имя своей учетной записи, а затем **выберите "Выйти".**

5. Во sign in with the new domain and your same password.

Вы также можете использовать PowerShell для перемещения пользователей в другой домен. Дополнительные сведения см. в под названием [Set-MsolUserPrincipalName.](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) Чтобы установить домен по умолчанию, используйте [Set-MsolDomain.](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0)

::: moniker-end

::: moniker range="o365-germany"

1. Перейдите **к** \> **"Активные пользователи"** и выберите свое имя в списке.

2. В разделе **"Имя пользователя / Электронная почта"** выберите "Изменить", а затем выберите другой домен. 

3. Select **Set as primary** > **Save** > **Close**.
  
4. В верхней части выберите имя своей учетной записи, а затем **выберите "Выйти".**

5. Во sign in with the new domain and your same password.

Вы также можете использовать PowerShell для перемещения пользователей в другой домен. Дополнительные сведения см. в перенастройке [Set-MsolUserPrincipalName.](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) Чтобы установить домен по умолчанию, используйте [Set-MsolDomain.](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0)

::: moniker-end

::: moniker range="o365-21vianet"

1. Перейдите **к** \> **"Активные пользователи"** и выберите свое имя в списке.

2. В разделе **"Имя пользователя / Электронная почта"** выберите "Изменить", а затем выберите другой домен. 

3. Select **Set as primary** > **Save** > **Close**.
  
4. В верхней части выберите имя своей учетной записи, а затем **выберите "Выйти".**

5. Во sign in with the new domain and your same password.

Вы также можете использовать PowerShell для перемещения пользователей в другой домен. Дополнительные сведения см. в под названием [Set-MsolUserPrincipalName.](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) Чтобы установить домен по умолчанию, используйте [Set-MsolDomain.](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0)

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a>Шаг 2. Перемещение групп в другой домен

::: moniker range="o365-worldwide"

1. В Центре администрирования перейдите на **страницу** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">"Группы групп".</a>
  
2. Выберите имя группы, а затем на вкладке **"Общие"** в области "Адрес **электронной почты", "Основной"** выберите **"Изменить".**

3. В выпадаемом списке выберите другой домен.

4. Нажмите кнопку **Сохранить**, а затем — **Закрыть**. Повторите эти шаги для всех групп или списков рассылки, связанных с доменом, который вы хотите удалить.

::: moniker-end

::: moniker range="o365-germany"

1. В Центре <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">администрирования перейдите</a>на **страницу** > **"Группы групп".**

2. Выберите имя группы, а затем выберите **"Изменить** рядом с **именем".**

3. В выпадаемом списке выберите другой домен.

4. Нажмите кнопку **Сохранить**, а затем — **Закрыть**. Повторите эти шаги для всех групп или списков рассылки, связанных с доменом, который вы хотите удалить.

::: moniker-end

::: moniker range="o365-21vianet"

1. В Центре <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">администрирования перейдите</a>на **страницу** > **"Группы** групп".

2. Выберите имя группы, а затем выберите **"Изменить** рядом с **именем".**

3. В выпадаемом списке выберите другой домен.

4. Нажмите кнопку **Сохранить**, а затем — **Закрыть**. Повторите эти шаги для всех групп или списков рассылки, связанных с доменом, который вы хотите удалить.

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a>Шаг 3. Удаление старого домена

::: moniker range="o365-worldwide"

1. В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).

::: moniker-end

::: moniker range="o365-germany"

1. В Центре администрирования перейдите на страницу **"Домены** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">установки".</a>

::: moniker-end

::: moniker range="o365-21vianet"

1. В Центре администрирования перейдите на страницу **"Домены** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">установки".</a>

::: moniker-end
  
2. На странице **"Домены"** выберите домен, который нужно удалить.

3. В правой области выберите **"Удалить".**

4. Следуйте дополнительным запросам и выберите **"Закрыть".**

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a>Время, необходимое для удаления домена

Удаление домена в Microsoft 365 может занять всего 5 минут, если на него не ссылается множество групп безопасности, списков рассылки, пользователей и групп Microsoft 365. Если же домен используется очень широко, на его удаление может потребоваться несколько часов или один день.
  
Если у вас сотни или тысячи пользователей, используйте PowerShell, чтобы отправить им всем запрос, а затем перенести их в другой домен. В противном случае может оказаться, что нескольких пользователей нет в интерфейсе. В результате вы не сможете удалить домен и не сумеете определить причину. Дополнительные сведения см. в статье о командлете [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0). Чтобы задать домен по умолчанию, используйте командлет [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).
  
## <a name="still-need-help"></a>Требуется дополнительная помощь?

::: moniker range="o365-worldwide"

> [!NOTE]
> Не удается удалить домен [".onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) из вашей учетной записи.
  
Не получилось? Возможно, ваш домен необходимо удалить вручную. [Позвоните нем](../contact-support-for-business-products.md), и мы поможем вам это сделать.
  
::: moniker-end

## <a name="related-articles"></a>Статьи по теме

[Вопросы и ответы о доменах](../setup/domains-faq.yml)

[Переход на другой план Microsoft 365 для бизнеса](../../commerce/subscriptions/switch-to-a-different-plan.md)

[Отмена подписки](../../commerce/subscriptions/cancel-your-subscription.md)
