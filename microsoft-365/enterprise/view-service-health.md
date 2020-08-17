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
description: Просмотрите состояние работоспособности служб Microsoft 365, прежде чем позвонить в службу поддержки, чтобы проверить, есть ли активные прерывания.
ms.openlocfilehash: 49f7d3afd3c19cd4e9b6486db580082fe933b997
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693483"
---
# <a name="how-to-check-microsoft-365-service-health"></a>Проверка работоспособности службы Microsoft 365

[![Надпись, оповещающая об изменении Центра администрирования. Дополнительные сведения см. на сайте aka.ms/aboutM365preview.](../media/O365-Admin-AdminCenterChanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview?view=o365-worldwide)

Вы можете просмотреть работоспособность служб Майкрософт, в том числе Office в Интернете, Yammer, Microsoft Dynamics CRM и облачных службах управления мобильными устройствами, на странице **работоспособность службы** в [центре администрирования Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339). If you are experiencing problems with a cloud service, you can check the service health to determine whether this is a known issue with a resolution in progress before you call support or spend time troubleshooting.

Если вы не можете войти на портал служб, вы можете использовать [страницу состояния службы](https://status.office365.com) , чтобы проверить наличие известных проблем, мешающих выполнению входа в клиент.
  
### <a name="how-to-check-service-health"></a>Проверка работоспособности службы

1. Перейдите в центр администрирования Microsoft 365 [https://admin.microsoft.com](https://go.microsoft.com/fwlink/p/?linkid=2024339) и войдите с помощью учетной записи администратора.

    > [!NOTE]
    > Для просмотра сведений о работоспособности требуется роль глобального администратора или администратора службы. Чтобы разрешить администраторам Exchange, SharePoint и Skype для бизнеса просматривать сведения о работоспособности служб, необходимо также назначить им роль администратора служб. Дополнительные сведения о ролях, которые могут просматривать работоспособность службы, приведены в статье [сведения о ролях администратора](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide#roles-available-in-the-microsoft-365-admin-center).
  
2. Если вы не используете новый центр администрирования, на **домашней** странице в правом верхнем углу установите переключатель в поле **попробовать новый центр администрирования** .

3. Чтобы просмотреть работоспособность службы, в центре администрирования перейдите к **Health**  >  **работоспособности службы**работоспособности или выберите карточку **работоспособности службы** на **панели мониторинга "Домашняя страница"**. Карточка панели мониторинга указывает на наличие активных неполадок службы и ссылку на подробную страницу " **работоспособность службы** ".
  
4. На странице " **работоспособность службы** " состояние работоспособности каждой облачной службы отображается в формате таблицы.

   ![View of current issues in service health](../media/service-health-all-services.png)

На вкладке **все службы** (представление по умолчанию) отображаются все службы и их текущее состояние работоспособности. Значок и столбец **состояния** указывают состояние каждой службы. 

Чтобы отфильтровать представление до служб, на которых наблюдается инцидент, перейдите на вкладку **инциденты** в верхней части страницы. При выборе вкладки **рекомендации** отображаются только службы, на которые в настоящее время опубликованы рекомендации. 

На вкладке **Журнал** отображается история инцидентов и рекомендаций, которые были устранены.

Если у вас возникла проблема со службой Microsoft 365, и она не отображается в списке на странице **работоспособность службы** , сообщите нам о ней, выбрав пункт **сообщить о неполадке**и заполнив краткую форму. Мы рассмотрим связанные данные и отчеты от других организаций, чтобы узнать, насколько распространена эта неполадка, и если она поступила с помощью нашей службы. Если это так, мы добавим его в качестве нового инцидента или рекомендаций на странице **работоспособность службы** , где можно отслеживать его решение. Если он не отображается в списке в течение 30 минут, обратитесь в службу поддержки, чтобы устранить эту проблему.

Чтобы подписаться на уведомления о новых инцидентах, влияющих на ваш клиент и состояние активного инцидента, выберите **настройки**, щелкните **Отправить уведомления о работоспособности в сообщении электронной почты**, а затем укажите:

- До двух адресов электронной почты.
- Требуются ли уведомления об инцидентах или рекомендациях
- Службы, для которых требуется уведомление

> [!NOTE]
> Для каждого администратора могут быть заданы параметры, а для каждой учетной записи администратора задано указанное выше количество.

> [!TIP]
> Вы также можете использовать [приложение Microsoft 365 Admin](https://go.microsoft.com/fwlink/p/?linkid=627216) на мобильном устройстве для просмотра работоспособности служб, что является прекрасным способом поддержания актуальности при push-уведомлениях. 
  
### <a name="view-details-of-posted-service-health"></a>Просмотр опубликованных сведений о работоспособности службы

В представлении **все службы** при выборе состояния службы откроется сводное представление рекомендаций или инцидентов.
  
![Снимок экрана, на котором показаны рекомендации по службам](../media/service-health-advisory.png)

В сводку включена следующая информация:

- **Заголовок** — сводка проблемы.
- **Service** — имя затронутой службы.
- **ID** — числовой идентификатор проблемы.
- **Status (состояние** ) — как эта проблема влияет на службу.
- **Время начала** — время начала выпуска.
- **Последнее обновление** — время последнего обновления сообщения о работоспособности службы. Мы получаем частые сообщения, которые помогут вам узнать, как мы работаем в процессе применения решения.

Выберите заголовок проблемы, чтобы просмотреть страницу сведений о проблемах с дополнительными сведениями об этой ошибке, включая [историю](#history) всех сообщений, опубликованных во время работы над решением.

![Снимок экрана с подробными сведениями о проблемах](../media/service-health-advisory-detail.png)

### <a name="translate-service-health-details"></a>Перевод сведений о работоспособности службы

Так как сведения о работоспособности служб публикуются в режиме реального времени, они предлагаются только на английском языке и не переводятся автоматически. Чтобы перевести объяснения, выполните следующие действия:
  
1. Перейдите на сайт [Переводчика](https://www.bing.com/translator/).

2. На странице **Работоспособность службы** выберите инцидент или рекомендацию. В разделе **Показать сведения** скопируйте текст.

3. Вставьте текст в Переводчик и нажмите кнопку **Translate** (Перевести).

### <a name="definitions"></a>Определения

В большинстве случаев службы будут отображаться как работоспособные без дополнительных сведений. Если в службе возникла проблема, выводится инцидент или рекомендация, а также сведения о текущем состоянии.
  
> [!TIP]
> Запланированные события обслуживания не отображаются в работоспособности службы. Вы можете отслеживать запланированные события обслуживания, начиная с самого начала и заканчивая **центром сообщений**. Фильтрация по сообщениям, отнесенным к плану изменения, чтобы узнать, когда будет выполняться изменение, и как подготовиться к работе. Более подробную информацию можно найти [в центре сообщений в Microsoft 365](https://support.office.com/article/38fb3333-bfcc-4340-a37b-deda509c2093) .
  
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
|**Ложное срабатывание** | После подробного изучения мы подтвердили, что служба является работоспособной и работает так же, как задумано. Не было замечено ни одного воздействия на службу или причина сбоя возникла за пресбоями службы. |
|**Отчет после инцидента опубликован** | Мы опубликовали отчет об инциденте POST для конкретной проблемы, включающей в себя сведения о корневой причине и дальнейших действиях, чтобы избежать возникновения подобной проблемы. |

### <a name="history"></a>History

Работоспособность службы позволяет просматривать текущее состояние работоспособности и просматривать историю всех помощников и инцидентов обслуживания, которые затронули ваш клиент за последние 30 дней. Чтобы просмотреть прошлую работоспособность всех служб, выберите **Просмотр журнала** на странице сведений о проблемах.
  
![Show link to health history](../media/service-health-view-history.png)
  
Появится список всех сообщений о работоспособности службы, опубликованных за выбранный период времени, как показано ниже:
  
![View service health history](../media/service-health-history.png)
  
Разверните любую строку, чтобы просмотреть дополнительные сведения об этой ошибке.
  
Для получения дополнительных сведений о приверженности к времени работы ознакомьтесь со статьей " [прозрачные операции" в Microsoft 365](https://go.microsoft.com/fwlink/?linkid=848695).

## <a name="related-topics"></a>Связанные статьи

[Отчеты об активности в центре](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) 
 администрирования Microsoft 365 [Параметры центра сообщений](https://docs.microsoft.com/microsoft-365/admin/manage/message-center?view=o365-worldwide#preferences11)