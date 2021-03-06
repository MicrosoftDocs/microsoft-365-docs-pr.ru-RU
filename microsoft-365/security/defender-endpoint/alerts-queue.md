---
title: Просмотр и организация очереди оповещений Microsoft Defender для конечных точек
description: Узнайте о том, как работают очереди оповещения Microsoft Defender для endpoint, а также о сортировке и фильтрации списков оповещений.
keywords: оповещения, очереди, очередь оповещений, сортировка, порядок, фильтр, управление оповещениями, новые, в процессе выполнения, разрешенные, новые, время в очереди, серьезность, период времени, оповещений экспертов по угрозам Майкрософт
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
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 03/27/2020
ms.technology: mde
ms.openlocfilehash: 48a3ff8dba5bccd62d7d43b295c136a814056a15
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934337"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-alerts-queue"></a>Просмотр и организация очереди оповещений Microsoft Defender для конечных точек

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Защитник для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)

>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-alertsq-abovefoldlink) 

Очередь **оповещений** показывает список оповещений, которые были помечены с устройств в сети. По умолчанию очередь отображает оповещения, которые отображаются в течение последних 30 дней в групповом представлении. Последние оповещений показываются в верхней части списка, помогая сначала увидеть самые последние оповещения.

> [!NOTE]
> Очередь оповещений значительно сокращается с помощью автоматического расследования и исправлений, что позволяет специалистам по операциям безопасности сосредоточиться на более сложных угрозах и других инициативах с высоким значением. Если оповещение содержит поддерживаемую сущность для автоматического расследования (например, файла) на устройстве с поддерживаемой операционной системой, может начаться автоматическое расследование и исправление. Дополнительные сведения об автоматизированных расследованиях см. в [обзоре автоматизированных расследований.](automated-investigations.md)

Существует несколько вариантов настройки представления очереди оповещений. 

В верхней части навигации можно:

- Выбор сгруппивного представления или представления списка
- Настройка столбцов для добавления или удаления столбцов 
- Выберите элементы, которые будут показываться на странице
- Перемещение между страницами
- Применение фильтров

![Изображение очереди оповещений](images/alerts-queue-list.png)

## <a name="sort-filter-and-group-the-alerts-queue"></a>Сортировка, фильтрация и группа очереди оповещений

Вы можете применить следующие фильтры, чтобы ограничить список оповещений и получить более целенаправленное представление оповещений.

### <a name="severity"></a>Серьезность

Серьезность оповещений | Описание
:---|:---
Фишинговое сообщение с </br>(Красный) | Оповещений, обычно замеченных, связанных с расширенными постоянными угрозами (APT). Эти оповещения указывают на высокий риск из-за серьезности ущерба, который они могут нанести устройствам. В качестве примеров можно привести такие действия, как кража учетных данных, действия вымогателей, не связанные с какой-либо группой, взлом датчиков безопасности или вредоносные действия, указывающие на действия человеческого противника.
Средний </br>(Оранжевый) | Оповещения из обнаружение и нейтрализация атак на конечные точки поведения после нарушения, которые могут быть частью передовой постоянной угрозы (APT). Это включает наблюдаемое поведение, типичное для этапов атаки, аномальное изменение реестра, выполнение подозрительных файлов и так далее. Хотя некоторые из них могут быть частью внутреннего тестирования безопасности, оно требует расследования, так как оно также может быть частью предварительной атаки.
Низкие </br>(Желтый) | Оповещения об угрозах, связанных с распространенными вредоносными программами. Например, средства взлома, средства взлома без вредоносных программ, такие как запуск команд разведки, журналы очистки и т. д., которые часто не указывают на передовую угрозу, направленную на организацию. Он также может быть от изолированного тестирования средства безопасности пользователем в вашей организации.
Информационный </br>(Серый) | Оповещения, которые не могут считаться вредными для сети, но могут повысить осведомленность организации о безопасности при возможных проблемах безопасности.

#### <a name="understanding-alert-severity"></a>Понимание серьезности оповещений

антивирусная программа в Microsoft Defender (Microsoft Defender AV) и Defender for Endpoint alert severities are different because they represent different scopes.

Степень серьезности угрозы av Защитника Майкрософт представляет абсолютную серьезность обнаруженной угрозы (вредоносных программ) и назначена в зависимости от потенциального риска для отдельного устройства в случае заражения.

Серьезность оповещения Defender для конечной точки представляет серьезность обнаруженного поведения, фактический риск для устройства, но что еще более важно , потенциальный риск для организации.

Например:

- Серьезность оповещения Защитника для конечных точек об обнаруженной угрозе AV Microsoft Defender, которая была полностью предотвращена и не заразила устройство, классифицируются как "Информационная", так как фактические повреждения не были повреждены.
- Предупреждение о коммерческой вредоносной программе было обнаружено при выполнении, но заблокировано и исправлено microsoft Defender AV, классифицируются как "Низкий", так как это может привести к некоторому повреждению отдельного устройства, но не представляет никакой организационной угрозы.
- Предупреждение о вредоносных программах, обнаруженных при выполнении, которые могут представлять угрозу не только для отдельного устройства, но и для организации, независимо от того, было ли оно в конечном итоге заблокировано, может быть ранжировано как "Medium" или "High".
- Подозрительные поведенческие оповещений, которые не были заблокированы или исправлены, будут ранжированы как "Low", "Medium" или "High" с учетом тех же организационных соображений угрозы.

#### <a name="understanding-alert-categories"></a>Понимание категорий оповещений

Мы переопределили категории оповещений, чтобы привести их в соответствие с тактикой корпоративной атаки в матрице [](https://attack.mitre.org/tactics/enterprise/) [ATT MITRE&CK.](https://attack.mitre.org/) Новые имена категорий применяются для всех новых оповещений. Существующие оповещений будут хранить имена предыдущих категорий.

В таблице ниже перечислены текущие категории и их общая карта с предыдущими категориями. 

| Новая категория       | Имя категории API   | Обнаруженная активность или компонент угрозы                                                                                                 |
|----------------------|---------------------|-----------------------------------------------------------------------------------------------------------------------------------------|
| Collection           | Collection          | Поиск и сбор данных для эксфильтрации                                                                                         |
| Командно-диспетчерский контроль  | CommandAndControl   | Подключение к сетевой инфраструктуре, управляемой злоумышленниками, для передачи данных или получения команд                                          |
| Доступ к учетным данным    | CredentialAccess    | Получение допустимых учетных данных для расширения контроля над устройствами и другими ресурсами в сети                                       |
| Уклонение от защиты      | DefenseEvasion      | Избегание элементов управления безопасностью, например отключение приложений безопасности, удаление имплантатов и запуск корневых наборов                        |
| Обнаружение            | Обнаружение           | Сбор сведений о важных устройствах и ресурсах, таких как компьютеры администратора, контроллеры домена и файловые серверы  |
| Выполнение            | Выполнение           | Запуск средств злоумышленника и вредоносного кода, включая raTs и backdoors                                                             |
| Exfiltration         | Exfiltration        | Извлечение данных из сети во внешнее, контролируемое злоумышленником расположение                                                         |
| Exploit              | Exploit             | Использование кода и возможной эксплуатации                                                                                       |
| Начальный доступ       | InitialAccess       | Получение начального входа в целевую сеть, обычно связанное с угадать пароль, эксплойтами или фишинговыми электронными письмами                      |
| Lateral movement     | LateralMovement     | Перемещение между устройствами в целевой сети для достижения критически важных ресурсов или сохранения сети                                |
| Вредоносные программы              | Вредоносные программы             | Backdoors, trojans and other types of malicious code                                                                                 |
| Упорство          | Упорство         | Создание точек extensibility autostart (ASEPs), чтобы оставаться активными и выживать при перезапуске системы                                        |
| Эскалация привилегий | PrivilegeEscalation | Получение более высоких уровней разрешений для кода, запуская его в контексте привилегированного процесса или учетной записи                         |
| Вымогателей           | Вымогателей          | Вредоносные программы, которые шифруют файлы и вымогают оплату для восстановления доступа                                                                     |
| Подозрительное действие  | SuspiciousActivity  | Нетипичная активность, которая может быть вредоносным по программам или частью атаки                                                                 |
| Нежелательное программное обеспечение    | UnwantedSoftware    | Приложения и приложения с низкой репутацией, которые влияют на производительность и пользовательский интерфейс; обнаружено как потенциально нежелательные приложения (PUAs) |

### <a name="status"></a>Состояние

Список оповещений можно ограничить в зависимости от их состояния.

### <a name="investigation-state"></a>Состояние исследования

Соответствует состоянием автоматического расследования.

### <a name="category"></a>Category

Вы можете фильтровать очередь для отображения определенных типов вредоносных действий.

### <a name="assigned-to"></a>Кому назначено

Вы можете выбрать между отображением оповещений, которые назначены вам, или автоматизацией.

### <a name="detection-source"></a>Источник обнаружения

Выберите источник, который вызвал обнаружение оповещений. эксперты Майкрософт по угрозам участники предварительного просмотра теперь могут фильтровать и просматривать обнаружения из новой службы охоты, управляемой специалистами по угрозам.

>[!NOTE]
>Антивирусный фильтр появится только в том случае, если устройства антивирусная программа в Microsoft Defender как средство защиты от антивируса по умолчанию в режиме реального времени.

| Источник обнаружения                  | Значение API                  |
|-----------------------------------|----------------------------|
| Датчики третьей стороны                 | ThirdPartySensors          |
| Защита от вирусов                         | WindowsDefenderAv          |
| Автоматическое расследование           | Автоматическаяинвестигация     |
| Настраиваемый обнаружение                  | CustomDetection            |
| Настраиваемый TI                         | CustomerTI                 |
| EDR                               | WindowsDefenderAtp         |
| Microsoft 365 Defender            | MTP                        |
| Microsoft Defender для Office 365 | OfficeATP                  |
| Эксперты Майкрософт по угрозам          | ThreatExperts              |
| SmartScreen                       | WindowsDefenderSmartScreen |

### <a name="os-platform"></a>Платформа ОС

Ограничить представление очереди оповещений, выбрав платформу ОС, интересуемую исследованием.

### <a name="device-group"></a>Группа устройств

Если у вас есть определенные группы устройств, которые вам интересны для проверки, можно выбрать группы, чтобы ограничить представление очереди оповещений. 

### <a name="associated-threat"></a>Связанная угроза

Используйте этот фильтр, чтобы сосредоточиться на оповещениях, связанных с угрозами высокого профиля. Полный список громких угроз можно увидеть в [аналитике угроз.](threat-analytics.md)

## <a name="related-topics"></a>Статьи по теме

- [Управление оповещениями Защитника Майкрософт для конечных точек](manage-alerts.md)
- [Исследование оповещений Microsoft Defender для конечных точек](investigate-alerts.md)
- [Исследование файла, связанного с оповещением Microsoft Defender для конечных точек](investigate-files.md)
- [Исследование устройств в списке Устройств конечных точек Microsoft Defender для конечных точек](investigate-machines.md)
- [Исследование IP-адреса, связанного с оповещением Microsoft Defender for Endpoint](investigate-ip.md)
- [Исследование домена, связанного с оповещением Microsoft Defender for Endpoint](investigate-domain.md)
- [Исследование учетной записи пользователя в Microsoft Defender для конечной точки](investigate-user.md)
