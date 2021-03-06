---
title: Проверка работоспособности службы Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365P_ServiceHealthModern
- O365M_ServiceHealthModern
- O365E_ViewStatusServices
- O365E_ServiceHealthModern
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- BCS160
- IWA160
ms.assetid: 932ad3ad-533c-418a-b938-6e44e8bc33b0
description: Просмотреть состояние состояния Microsoft 365, прежде чем вызывать службу поддержки, чтобы узнать, существует ли активное прерывание службы.
ms.openlocfilehash: 95ab260b4950d261eed1288b8fdf1f59883ff15f
ms.sourcegitcommit: 17d82e5617f0466eb825e15ab88594afcdaf4437
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2021
ms.locfileid: "53300409"
---
# <a name="how-to-check-microsoft-365-service-health"></a>Проверка работоспособности службы Microsoft 365

[![Надпись, оповещающая об изменении Центра администрирования. Дополнительные сведения см. на сайте aka.ms/aboutM365preview.](../media/O365-Admin-AdminCenterChanging.png)](/office365/admin/microsoft-365-admin-center-preview?preserve-view=true&view=o365-worldwide)

Вы можете просмотреть состояние службы Майкрософт, включая Office в Интернете, Yammer, Microsoft Dynamics CRM и облачные службы управления мобильными устройствами,  на странице Службы здравоохранения в [Центр администрирования Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339). If you are experiencing problems with a cloud service, you can check the service health to determine whether this is a known issue with a resolution in progress before you call support or spend time troubleshooting.

Если вы не можете войти в центр администрирования, [](https://status.office365.com) вы можете использовать страницу состояния службы для проверки известных проблем, препятствующих входу в клиент.  Кроме того, зарегистрироваться, чтобы следовать за [нами @MSFT365status](https://twitter.com/MSFT365Status) в Twitter, чтобы увидеть информацию о некоторых событиях.

## <a name="how-to-check-service-health"></a>Проверка работоспособности службы

1. Перейдите в Центр администрирования Microsoft 365 [https://admin.microsoft.com](https://go.microsoft.com/fwlink/p/?linkid=2024339) и войдите в учетную запись администратора.

    > [!NOTE]
    > Люди, которым назначена роль администратора глобальной службы или администратора службы, могут просматривать состояние службы. Чтобы разрешить администраторам Exchange, SharePoint и Skype для бизнеса просматривать сведения о работоспособности служб, необходимо также назначить им роль администратора служб. Дополнительные сведения о ролях, которые могут просматривать состояние службы, см. в [статью О ролях администратора.](../admin/add-users/about-admin-roles.md?preserve-view=true&view=o365-worldwide#commonly-used-microsoft-365-admin-center-roles)

2. Чтобы просмотреть состояние службы, в центре администрирования перейдите в службу здравоохранения или выберите карточку здоровья службы  >  на панели **мониторинга home.**  На карточке мониторинга указывается, существует ли активная проблема службы, и ссылки на подробную страницу **здоровья** службы.

3. На странице **Здоровье службы** состояние здоровья каждой облачной службы отображается в формате таблицы.

   ![View of current issues in service health](../media/service-health-all-services.png)

На **вкладке Все службы** (представление по умолчанию) показаны все службы, текущее состояние их здоровья и все активные инциденты или советы. Значок и состояние в столбце **Здоровье** указывают состояние каждой службы.

При активном инциденте или консультации для службы они будут перечислены непосредственно под именем службы в вложенной таблице. Вы можете свернуть вложенную таблицу, чтобы скрыть инциденты или советы в этом представлении, щелкнув значок chevron слева от имени службы.   

Чтобы отфильтровать представление, чтобы показать только все активные инциденты, выберите вкладку **Incidents** в верхней части страницы. Выбор вкладки **"Советники"** будет показывать только все размещенные активные советы.

На **вкладке История** показаны все инциденты и советы, которые были устранены в течение последних семи или 30 дней.

Если у вас возникли проблемы со службой Microsoft 365 и вы не видите  ее, указанную на странице здоровье службы, сообщите нам об этом, выбрав отчет о проблеме и заполнив короткую форму. Мы посмотрим на соответствующие данные и отчеты из других организаций, чтобы узнать, насколько широко распространена проблема и возникла ли она с помощью нашей службы. Если это произошло, мы добавим его в  качестве нового инцидента или рекомендации на странице здоровье службы, где можно отслеживать его разрешение. На **странице "Сообщаемая** проблема" покажут все проблемы, о которые клиент сообщил из этой формы и состояния.

Чтобы настроить представление о том, какие службы будут показываться на панели мониторинга, выберите настраиваемые представления "Настройки" и очистите почтовые ящики для служб, которые необходимо отфильтровать из представления панели мониторинга состояния  >  службы. Убедитесь, что для каждой службы, которую необходимо отслеживать, выбран почтовый ящик.

Чтобы подписаться на уведомления электронной почты о новых инцидентах, влияющих на изменения клиента и состояния для активного инцидента, выберите "Настройки электронной почты", нажмите кнопку   >   **Отправка** уведомлений об обогреве службы в электронной почте, а затем укажите:

- До двух адресов электронной почты.
- Нужны ли уведомления об инцидентах или консультациях
- Службы, для которых необходимо уведомление

Кроме того, вместо каждого события для службы можно подписаться на уведомления электронной почты для отдельных событий. Для этого выберите активную проблему, для получения обновлений уведомлений по электронной почте, выберите Управление уведомлениями для этой **проблемы,** а затем укажите: 
- До двух адресов электронной почты.

> [!NOTE]
> Каждый администратор может иметь свои настройки, и вышеуказанное ограничение в два адреса электронной почты — на учетную запись администратора.

> [!TIP]
> Вы также можете использовать приложение [Microsoft 365 Admin](https://go.microsoft.com/fwlink/p/?linkid=627216) на мобильном устройстве для просмотра состояния службы, что является отличным способом оставаться актуальным с push-уведомлениями.

### <a name="view-details-of-posted-service-health"></a>Просмотр опубликованных сведений о работоспособности службы

В **представлении "Все** службы" выберите название проблемы, чтобы просмотреть страницу сведений о проблеме, на которой показаны дополнительные сведения о проблеме, включая канал всех сообщений, которые были размещены во время работы над решением. 

[![Снимок экрана, на котором показана консультация по службе ](../media/service-health-advisory.png)](../media/service-health-advisory.png#lightbox)

В сводку включена следующая информация:

- **Название** — сводка проблемы.
- **ID** — числимый идентификатор проблемы.
- **Служба** . Имя пострадавшей службы.
- **Последнее обновление** — последний раз, когда было обновлено сообщение о состоянии службы.
- **Предполагаемое время запуска** — предполагаемое время начала проблемы.
- **Состояние** . Как эта проблема влияет на службу.
- **Влияние пользователя** — краткое описание влияния этой проблемы на конечного пользователя.
- **Все обновления** . Мы вывешим частые сообщения, чтобы вы знали о том, как мы продвинулись в применении решения.

![Снимок экрана, на котором показаны сведения о проблеме](../media/service-health-advisory-detail.png)

### <a name="translate-service-health-details"></a>Перевод сведений о работоспособности службы

Мы используем машинный перевод для автоматического отображения сообщений на предпочтительном языке. Дополнительные сведения о том, как настроить язык, читайте в публикации [Language translation for Message](/microsoft-365/admin/manage/language-translation-for-message-center-posts) Center.

### <a name="definitions"></a>Определения

Большую часть времени службы будут отображаться как полезные без дополнительных сведений. Если в службе возникла проблема, выводится инцидент или рекомендация, а также сведения о текущем состоянии.

> [!TIP]
> Запланированные события обслуживания не показаны в состоянии обслуживания. Вы можете отслеживать запланированные события обслуживания, оставаясь в курсе событий в Центре **сообщений.** Фильтрация сообщений, классифицируются как План изменений, чтобы узнать, когда произойдет изменение, его влияние и как к этому подготовиться. Дополнительные [сведения см. в Microsoft 365](https://support.office.com/article/38fb3333-bfcc-4340-a37b-deda509c2093) центре сообщений.

### <a name="incidents-and-advisories"></a>Инциденты и рекомендации

| Значок | Описание |
|:-----|:-----|
|![Information icon for advisory](../media/a7f5fd21-c760-4948-9bc1-50f7c8070e28.png)|Если для службы выводятся рекомендации, это значит, что нам известно о проблеме, которая касается некоторых пользователей, но служба по-прежнему доступна. В рекомендации часто указывается временное решение проблемы, которая может быть непостоянной или иметь ограниченное воздействие.  <br/> |
|![Exclamation point icon for incident](../media/a636db57-6083-44dc-bbd5-556850804f17.png)|Если для службы указан инцидент, это критическая проблема, а служба или ее основные функции недоступны. Например, может не работать отправка и получение электронной почты или вход в службу. Инциденты оказывают заметное влияние на пользователей. При возникновении инцидентов мы будем публиковать на информационной панели новости об их изучении и устранении, а также сообщения о том, что проблема решена.  <br/> |

### <a name="status-definitions"></a>Определения состояний

| Status | Определение |
|:-----|:-----|
|**Изучается** | Мы знаем о возможной проблеме и собираем дополнительные сведения о ней и ее влиянии. |
|**Производительность службы снижена** | Мы подтвердили, что проблема может повлиять на использование служб или функций. Это состояние может отображаться, если служба работает медленнее, чем обычно, периодически возникают прерывания или если недоступна определенная функция. |
|**Работа службы прервана** | Вы увидите это состояние, если определено, что проблема влияет на доступ к службе. В этом случае проблема является значительной и ее можно воспроизвести. |
|**Восстановление службы** | Причина проблемы определена, мы знаем, как ее решить, и восстанавливаем службу. |
|**Длительное восстановление** | Это состояние указывает на то, что работа над восстановлением службы идет, но пройдет некоторое время, прежде чем она станет доступна для всех затронутых систем. Это состояние также отображается, если мы применили временное исправление, чтобы уменьшить влияние проблемы, пока готовится постоянное исправление. |
|**Исследование приостановлено** | Это состояние отображается, если для дальнейшего исследования необходимы дополнительные сведения. В случае если от вас требуются определенные действия, мы дадим вам знать, какие данные или журналы нам нужны. |
|**Служба восстановлена** | Мы убедились, что проблема была решена, а работоспособность службы восстановлена. Чтобы узнать, в чем было дело, просмотрите сведения о проблеме. |
|**Ложный срабатыв** | После подробного исследования мы подтвердили, что служба работает в штатном режиме. Никакого влияния на службу не наблюдалось, а причина инцидента возникла за пределами службы. |
|**Опубликован отчет о после инцидентах** | Мы опубликовали отчет об инцидентах после публикации для определенной проблемы, которая включает сведения о первопричинах и последующие действия для обеспечения того, чтобы подобная проблема не повторялась. |

### <a name="message-post-types"></a>Типы сообщений

| Тип | Определение |
|:-----|:-----|
|**Быстрое обновление** | Короткие и частые дополнительные обновления для инцидентов с широким влиянием, доступные всем клиентам. |
|**Дополнительные сведения** | Эти дополнительные сообщения будут предоставлять более подробные технические сведения и сведения о разрешении, чтобы обеспечить более глубокую видимость в обработке инцидентов. Это доступно для клиентов, которые соответствуют тем же требованиям, изложенным для Exchange Online [мониторинга](/microsoft-365/enterprise/microsoft-365-exchange-monitoring?view=o365-worldwide#requirements), |

### <a name="history"></a>History

Служба здравоохранения позволяет просмотреть текущее состояние здоровья и просмотреть историю любых консультантов и инцидентов, которые затронули клиента за последние 30 дней. Чтобы просмотреть прошлое состояние всех служб, выберите **представление "История".**

Дополнительные сведения о нашем обязательстве по работе см. в [Microsoft 365.](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)

## <a name="related-topics"></a>Статьи по теме

[Отчеты о действиях в Центр администрирования Microsoft 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

[Предпочтения центра сообщений](../admin/manage/message-center.md?preserve-view=true&view=o365-worldwide#preferences)

[Проверка состояния Windows в центре администрирования](/windows/deployment/update/check-release-health)
