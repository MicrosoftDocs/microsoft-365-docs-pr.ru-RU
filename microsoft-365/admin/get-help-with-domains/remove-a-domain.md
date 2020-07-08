---
title: Удаление домена
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
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
ms.openlocfilehash: 6f5e36a897316c8cdc057a725957c54e7eb53edc
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/08/2020
ms.locfileid: "45079765"
---
# <a name="remove-a-domain"></a>Удаление домена

::: moniker range="o365-21vianet"

> [!NOTE]
> Изменяется Центр администрирования. Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end
  
 Если вы не нашли то, что вы ищете, обратитесь к разделу **[вопросы и ответы по доменам](../setup/domains-faq.md)**. 
  
Вы удаляете домен, так как хотите добавить его в другой план подписки Microsoft 365? Или вам нужно просто отменить свою подписку? Вы можете [сменить план или подписку](../../commerce/subscriptions/switch-to-a-different-plan.md) либо [отменить подписку](../../commerce/subscriptions/cancel-your-subscription.md).
  
### <a name="step-1-move-users-to-another-domain"></a>Шаг 1: перемещение пользователей в другой домен

#### <a name="move-users"></a>Перемещение пользователей

::: moniker range="o365-worldwide"

1. Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">центр администрирования</a>.

2. Выберите пункт **Пользователи** > **Активные пользователи**.

3. Установите флажки рядом с именами всех пользователей, которых требуется переместить.

4. В верхней части страницы нажмите кнопку **Дополнительные параметры** (**...**), а затем выберите команду **изменить домены**.

5. В области **изменить домены** выберите другой домен.

You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.

::: moniker-end

::: moniker range="o365-germany"

1. Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">центр администрирования</a>.  

2. Выберите пункт **Пользователи** > **Активные пользователи**.

3. Установите флажки рядом с именами всех пользователей, которых требуется переместить.

4. В верхней части страницы выберите **Дополнительные** > **домены редактирования**.

5. В области **изменить домены** выберите другой домен.
  
You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.

::: moniker-end

::: moniker range="o365-21vianet"

1. Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">центр администрирования</a>.  

2. Выберите пункт **Пользователи** > **Активные пользователи**.

3. Установите флажки рядом с именами всех пользователей, которых требуется переместить.

4. В верхней части страницы выберите **Дополнительные** > **домены редактирования**.

5. В области **изменить домены** выберите другой домен.
  
You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.

::: moniker-end

#### <a name="move-yourself"></a>Самостоятельное перемещение

::: moniker range="o365-worldwide"

1. Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">центр администрирования</a>.

2. Перейдите к **Users** разделу \> **Активные пользователи**пользователей и выберите свою учетную запись из списка.

3. На вкладке **учетная запись** выберите пункт **Управление именем пользователя**, а затем выберите другой домен.
  
4. В верхней части выберите имя учетной записи, а затем нажмите **выйти**.

5. Выполните вход с новым доменом и тем же паролем.

Вы также можете использовать PowerShell для перемещения пользователей в другой домен. Для получения дополнительных сведений см. [Set – мсолусерпринЦипалнаме](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) . Чтобы задать домен по умолчанию, используйте [Set – мсолдомаин](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).

::: moniker-end

::: moniker range="o365-germany"

1. Перейдите к **Users** разделу \> **Активные пользователи**пользователей и выберите свое имя в списке.

2. В разделе **имя пользователя и электронная почта** нажмите кнопку **изменить**, а затем выберите другой домен.

3. Выберите **задать в качестве основного** > **сохранения** > **закрытия**.
  
4. В верхней части выберите имя учетной записи, а затем нажмите **выйти**.

5. Выполните вход с новым доменом и тем же паролем.

Вы также можете использовать PowerShell для перемещения пользователей в другой домен. Для получения дополнительных сведений см. [Set – мсолусерпринЦипалнаме](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) . Чтобы задать домен по умолчанию, используйте [Set – мсолдомаин](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).

::: moniker-end

::: moniker range="o365-21vianet"

1. Перейдите к **Users** разделу \> **Активные пользователи**пользователей и выберите свое имя в списке.

2. В разделе **имя пользователя и электронная почта** нажмите кнопку **изменить**, а затем выберите другой домен.

3. Выберите **задать в качестве основного** > **сохранения** > **закрытия**.
  
4. В верхней части выберите имя учетной записи, а затем нажмите **выйти**.

5. Выполните вход с новым доменом и тем же паролем.

Вы также можете использовать PowerShell для перемещения пользователей в другой домен. Для получения дополнительных сведений см. [Set – мсолусерпринЦипалнаме](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) . Чтобы задать домен по умолчанию, используйте [Set – мсолдомаин](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a>Шаг 2: перемещение групп в другой домен

::: moniker range="o365-worldwide"

1. В центре администрирования перейдите на **Groups** \> страницу <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">группы</a> группы.
  
2. Выберите имя группы, а затем на вкладке **Общие** в разделе **адрес электронной почты, основной**нажмите кнопку **изменить**.

3. Используйте раскрывающийся список для выбора другого домена.

4. Нажмите кнопку **Сохранить**, а затем — **Закрыть**. Повторите эти шаги для всех групп или списков рассылки, связанных с доменом, который вы хотите удалить.

::: moniker-end

::: moniker range="o365-germany"

1. В <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">центре администрирования</a>перейдите на **Groups** > страницу **группы** группы.

2. Выберите имя группы, а затем нажмите кнопку **изменить** рядом с **именем**.

3. Используйте раскрывающийся список для выбора другого домена.

4. Нажмите кнопку **Сохранить**, а затем — **Закрыть**. Повторите эти шаги для всех групп или списков рассылки, связанных с доменом, который вы хотите удалить.

::: moniker-end

::: moniker range="o365-21vianet"

1. В <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">центре администрирования</a>перейдите на **Groups** > страницу **группы** группы.

2. Выберите имя группы, а затем нажмите кнопку **изменить** рядом с **именем**.

3. Используйте раскрывающийся список для выбора другого домена.

4. Нажмите кнопку **Сохранить**, а затем — **Закрыть**. Повторите эти шаги для всех групп или списков рассылки, связанных с доменом, который вы хотите удалить.

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a>Шаг 3: удаление старого домена

::: moniker range="o365-worldwide"

1. В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).

::: moniker-end

::: moniker range="o365-germany"

1. В центре администрирования перейдите на страницу " **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">домены</a> установки".

::: moniker-end

::: moniker range="o365-21vianet"

1. В центре администрирования перейдите на страницу " **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">домены</a> установки".

::: moniker-end
  
2. На странице **Domains (домены** ) выберите домен, который требуется удалить.

3. В правой области нажмите кнопку **Удалить**.

4. Следуйте дополнительным приглашениям, а затем нажмите кнопку **Закрыть**.

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a>Время, необходимое для удаления домена

365 для удаления домена в случае отсутствия ссылок на группы безопасности, списки рассылки, пользователей и группы Майкрософт 365 может потребоваться до 5 минут. Если же домен используется очень широко, на его удаление может потребоваться несколько часов или один день.
  
If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain. Otherwise, it's possible for a handful of users to be missed in the UI, and then when you go to remove the domain, you won't be able to and you won't know why. See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information. To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).
  
## <a name="still-need-help"></a>Требуется дополнительная помощь?

::: moniker range="o365-worldwide"

> [!NOTE]
> Не удается удалить домен [".onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) из вашей учетной записи.
  
Still not working? Your domain might need to be manually removed. [Give us a call](../contact-support-for-business-products.md) and we'll help you take care of it!
  
::: moniker-end

## <a name="related-articles"></a>Статьи по теме

[Вопросы и ответы о доменах](../setup/domains-faq.md)

[Получение справки по доменам Microsoft 365](get-help-with-domains.md)

[Переход на другой план Microsoft 365 для бизнеса](../../commerce/subscriptions/switch-to-a-different-plan.md)

[Отмена подписки](../../commerce/subscriptions/cancel-your-subscription.md)
