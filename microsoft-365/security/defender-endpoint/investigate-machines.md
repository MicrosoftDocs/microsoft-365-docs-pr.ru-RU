---
title: Исследование устройств в списке устройств Defender для конечных точек
description: Изучите затронутые устройства, просмотрев оповещения, сведения о сетевом подключении, добавив теги и группы устройств и проверив состояние службы.
keywords: устройства, теги, группы, конечная точка, очередь оповещений, оповещений, имя устройства, домен, последний вид, внутренний IP, активные оповещения, категория угроз, фильтр, сортировка, проверка оповещений, сеть, подключение, тип, кража паролей, вымогателей, эксплойт, угроза, низкая серьезность, здоровье службы
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c89de5fbf5d5b4d5d5e53074109bc8884a271eea
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394897"
---
# <a name="investigate-devices-in-the-microsoft-defender-for-endpoint-devices-list"></a>Исследование устройств в списке Устройств конечных точек Microsoft Defender для конечных точек

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatemachines-abovefoldlink)

Изучите сведения о предупреждении, поднятом на определенном устройстве, чтобы определить другие действия или события, которые могут быть связаны с предупреждением или потенциальной областью нарушения.

> [!NOTE]
> В рамках процесса расследования или ответа можно собрать пакет исследований с устройства. Вот как: [сбор пакета исследований с устройств.](/microsoft-365/security/defender-endpoint/respond-machine-alerts#collect-investigation-package-from-devices)

Вы можете щелкнуть по затронутым устройствам всякий раз, когда увидите их на портале, чтобы открыть подробный отчет об этом устройстве. Затронутые устройства определены в следующих областях:

- [Список устройств](investigate-machines.md)
- [Очередь оповещений](alerts-queue.md)
- [Панель мониторинга операций безопасности](security-operations-dashboard.md)
- Любое отдельное оповещение
- Любое представление отдельных сведений о файле
- Представление любых IP-адресов или сведений о домене

При расследовании конкретного устройства вы увидите:

- Сведения о устройстве
- Действия реагирования
- Вкладки (обзор, оповещения, сроки, рекомендации по безопасности, инвентаризация программного обеспечения, обнаруженные уязвимости, отсутствующие ЦБ)
- Карты (активные оповещения, зарегистрированные на пользователях, оценка безопасности)

![Изображение представления устройства](images/specific-device.png)

> [!NOTE]
> Из-за ограничений продукта профиль устройства не рассматривает все кибер-доказательства при определении таймфрейма "Последний просмотр" (как видно на странице устройства).
> Например, значение "Последнее увиденное" на странице Устройство может показывать более старые временные рамки, несмотря на то, что в временной шкале машины доступны более последние оповещения или данные.

## <a name="device-details"></a>Сведения о устройстве

В разделе сведения об устройстве содержится информация, например, о состоянии домена, ОС и состояния здоровья устройства. Если на устройстве доступен пакет исследований, вы увидите ссылку, которая позволяет скачать пакет.

## <a name="response-actions"></a>Действия реагирования

Действия ответа, которые запускают по верхней части определенной страницы устройства и включают в себя:

- Управление тегами
- Изолировать устройство
- Ограничить выполнение приложения
- Запуск проверки на вирусы
- Сбор пакета исследования
- Инициировать сеанс живого ответа
- Инициировать автоматическое расследование
- Обратитесь к эксперту по угрозам
- Центр уведомлений

Действия реагирования можно принимать в центре действий, на определенной странице устройства или на определенной странице файла.

Дополнительные сведения о том, как действовать на устройстве, см. в этой информации. [](respond-machine-alerts.md)

Дополнительные сведения см. в [дополнительных сведениях о том, как исследовать объекты пользователей.](investigate-user.md)

## <a name="tabs"></a>Вкладки

Вкладки предоставляют соответствующие сведения о безопасности и предотвращении угроз, связанные с устройством. На каждой вкладке можно настроить столбцы, которые показаны, выбрав столбцы **Customize** из панели над заголовками столбцов.

### <a name="overview"></a>Обзор
На **вкладке Обзор** отображаются [карточки](#cards) для активных оповещений, зарегистрированных в пользователях, и оценки безопасности.

![Изображение вкладки обзор на странице устройства](images/overview-device.png)

### <a name="alerts"></a>Оповещения

Вкладка **Alerts** содержит список оповещений, связанных с устройством. Этот список является фильтрованной [](alerts-queue.md)версией очереди оповещений и показывает краткое описание оповещения, серьезности (высокая, средняя, низкая, информационная), состояния в очереди (новое, в процессе выполнения, разрешено), классификации (не установлено, ложное оповещение, истинное оповещение), состояния расследования, категории оповещения, который обращается к оповещению и последней активности. Вы также можете фильтровать оповещения.

![Изображение оповещений, связанных с устройством](images/alerts-device.png)

Когда выбран значок круга слева от оповещений, появляется вылет. На этой панели можно управлять оповещением и просматривать дополнительные сведения, такие как номер инцидента и связанные устройства. Одновременно можно выбрать несколько оповещений.

Чтобы просмотреть полное представление оповещений, включая график инцидентов и дерево процессов, выберите название оповещений.

### <a name="timeline"></a>Временная шкала

Вкладка **Timeline** предоставляет хронологическое представление событий и связанных с ними оповещений, которые наблюдались на устройстве. Это поможет вам соотнести все события, файлы и IP-адреса по отношению к устройству.

Временная шкала также позволяет выборочно сверлить события, которые произошли в течение определенного периода времени. Можно просмотреть временную последовательность событий, произошедших на устройстве за выбранный период времени. Для дальнейшего управления представлением можно фильтровать группы событий или настраивать столбцы.

>[!NOTE]
> Чтобы отобразить события брандмауэра, необходимо включить политику аудита, см. в статью [Подключение платформы фильтрации аудита.](/windows/security/threat-protection/auditing/audit-filtering-platform-connection)
>Брандмауэр охватывает следующие события
>
>- [5025](/windows/security/threat-protection/auditing/event-5025) — остановлена служба брандмауэра
>- [5031](/windows/security/threat-protection/auditing/event-5031) — приложение, заблокированное при приеме входящих подключений в сети
>- [5157](/windows/security/threat-protection/auditing/event-5157) — заблокированное подключение

![Изображение временной шкалы устройства с событиями](images/timeline-device.png)

Некоторые функции включают в себя:

- Поиск определенных событий
  - Используйте панели поиска для поиска определенных событий временной шкалы.
- Фильтрация событий с определенной даты
  - Выберите значок календаря в верхней левой части таблицы, чтобы отображать события за прошедший день, неделю, 30 дней или настраиваемый диапазон. По умолчанию установлена временная шкала устройства, которая отображает события за последние 30 дней.
  - Используйте временную шкалу, чтобы перейти к определенному моменту времени, выделив раздел. Стрелки на временной шкале выявляют автоматизированные исследования
- Экспорт подробных событий временной шкалы устройств
  - Экспорт временной шкалы устройства для текущей даты или определенного диапазона дат до семи дней.

Дополнительные сведения о некоторых событиях предоставляются в разделе **Дополнительные сведения.** Эти сведения зависят от типа события, например: 

- Contained by Application Guard - the web browser event was restricted by an isolated container
- Обнаружена активная угроза — обнаружение угрозы произошло во время запуска угрозы.
- Исправление не удалось — попытка устранения обнаруженной угрозы была вызвана, но не удалась
- Исправление успешно — обнаруженная угроза была остановлена и очищена
- Предупреждение, обходить стороной пользователя — Защитник Windows SmartScreen было отклонено и переопределено пользователем.
- Обнаружен подозрительный скрипт — обнаружен потенциально вредоносный сценарий
- Категория оповещений — если событие привело к генерации оповещений, предоставляется категория оповещений ("Лайтальное движение", например).

#### <a name="event-details"></a>Сведения о событиях
Выберите событие, чтобы просмотреть соответствующие сведения об этом событии. Панель отображает общие сведения о событиях. Когда применимы и доступны данные, также отображается график, на котором показаны связанные сущности и их связи.

Чтобы дополнительно инспектировать события и связанные [](advanced-hunting-overview.md) с ними события, можно быстро выполнить расширенный запрос на охоту, выбрав **Hunt для связанных событий.** Запрос возвращает выбранное событие и список других событий, произошедших примерно в одно и то же время на той же конечной точке.

![Изображение панели сведений о событии](images/event-details.png)

### <a name="security-recommendations"></a>Рекомендации по безопасности

**Рекомендации по безопасности создаются** в Microsoft Defender для функции управления & уязвимостей в [конечной](tvm-dashboard-insights.md) точке. Выбор рекомендации покажет панель, на которой можно просмотреть соответствующие сведения, такие как описание рекомендации и потенциальные риски, связанные с ее непринятия. Подробные [сведения см. в](tvm-security-recommendation.md) рекомендации по безопасности.

![Изображение вкладки рекомендации по безопасности](images/security-recommendations-device.png)

### <a name="software-inventory"></a>Перечень программного обеспечения

Вкладка **инвентаризации** программного обеспечения позволяет просматривать программное обеспечение на устройстве, а также любые слабые стороны или угрозы. Выбор имени программного обеспечения позволит вам просмотреть рекомендации по безопасности, обнаруженные уязвимости, установленные устройства и распространение версий. Сведения [о инвентаризации программного](tvm-software-inventory.md) обеспечения

![Изображение вкладки инвентаризации программного обеспечения](images/software-inventory-device.png)

### <a name="discovered-vulnerabilities"></a>Обнаруженные уязвимости

На **вкладке "Обнаруженные уязвимости"** показано имя, серьезность и сведения об угрозах обнаруженных уязвимостей на устройстве. При выборе определенных уязвимостей покажут описание и сведения.

![Изображение вкладки обнаруженных уязвимостей](images/discovered-vulnerabilities-device.png)

### <a name="missing-kbs"></a>Отсутствующие KBs
На **вкладке Missing KBs** перечислены отсутствующие обновления безопасности для устройства.

![Изображение отсутствующих вкладок kbs](images/missing-kbs-device.png)

## <a name="cards"></a>Карточки

### <a name="active-alerts"></a>Активные оповещения

На **карточке Advanced Threat Protection** Azure будет отображаться высокоуровневый обзор оповещений, связанных с устройством и уровнем риска, если вы включили функцию Microsoft Defender для удостоверений и есть активные оповещений. Дополнительные сведения можно получить в упражнении "Оповещение".

![Изображение карты активных оповещений](images/risk-level-small.png)

>[!NOTE]
>Для использования этой функции необходимо включить интеграцию в Microsoft Defender for Identity и Defender for Endpoint. В Defender for Endpoint вы можете включить эту функцию в расширенных функциях. Дополнительные сведения о том, как включить расширенные функции, см. в дополнительных [сведениях.](advanced-features.md)

### <a name="logged-on-users"></a>Вход в систему пользователей

В **карточке** входа в систему пользователей показано, сколько пользователей вошел в систему за последние 30 дней, а также наиболее и наименее часто используемых пользователей. Выбор ссылки "См. все пользователи" открывает области сведений, которая отображает сведения, такие как тип пользователя, войти в тип, и когда пользователь был первым и последним видел. Дополнительные сведения см. в [дополнительных сведениях о том, как исследовать объекты пользователей.](investigate-user.md)

![Изображение области пользовательских сведений](images/logged-on-users.png)
> [!NOTE]
> Значение пользователя "Самый частый" вычисляется только на основе данных пользователей, успешно воехавших в интерактивном режиме. Однако боковая часть "Все пользователи" вычисляет всевозможные логотипы пользователей, поэтому ожидается, что пользователи будут чаще видеться в стороне, учитывая, что эти пользователи могут не быть интерактивными.

### <a name="security-assessments"></a>Оценки безопасности

Карта **оценки безопасности показывает** общий уровень экспозиции, рекомендации по безопасности, установленное программное обеспечение и обнаруженные уязвимости. Уровень экспозиции устройства определяется совокупным воздействием ожидающих рекомендаций по безопасности.

![Изображение карты оценки безопасности](images/security-assessments.png)

## <a name="related-topics"></a>Статьи по теме

- [Просмотр и упорядочивание очереди оповещений Microsoft Defender для конечной точки](alerts-queue.md)
- [Управление оповещениями Защитника Майкрософт для конечных точек](manage-alerts.md)
- [Исследование оповещений Microsoft Defender для конечных точек](investigate-alerts.md)
- [Исследование файла, связанного с предупреждением Defender for Endpoint](investigate-files.md)
- [Исследование IP-адреса, связанного с оповещением Defender for Endpoint](investigate-ip.md)
- [Исследование домена, связанного с предупреждением Defender for Endpoint](investigate-domain.md)
- [Исследование учетной записи пользователя в Defender для конечной точки](investigate-user.md)
- [Рекомендация по безопасности](tvm-security-recommendation.md)
- [Инвентаризация программного обеспечения](tvm-software-inventory.md)
