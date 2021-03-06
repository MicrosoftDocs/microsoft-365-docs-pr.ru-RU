---
title: Exchange Online Protection (EOP)
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 09/18/2020
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: Узнайте, Exchange Online Protection (EOP) может помочь защитить организацию локальной электронной почты в автономных и гибридных средах.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a925b251ff79aec5acaa0b2c1da2aee3f5a6d70d
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930167"
---
# <a name="exchange-online-protection-overview"></a>Обзор Exchange Online Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online Protection (EOP) — это облачная служба фильтрации, которая защищает организацию от нежелательной почты, вредоносных программ и других угроз электронной почты. EOP включен во все организации Microsoft 365 с Exchange Online почтовыми ящиками.

> [!NOTE]
> EOP также сам по себе доступен для защиты локального почтового ящика и в гибридных средах для защиты Exchange почтовых ящиков. Дополнительные сведения см. [в Exchange Online Protection.](/exchange/standalone-eop/standalone-eop)

Действия по настройкам функций безопасности EOP и сравнение с добавленной безопасностью, которую вы получаете в Microsoft Defender для Office 365, см. в руб. Защита от [угроз.](protect-against-threats.md) Рекомендуемые параметры для функций EOP доступны в рекомендуемых параметрах для EOP и [Microsoft Defender для Office 365 безопасности.](recommended-settings-for-eop-and-office365.md)

В остальной части этой статьи объясняется, как работает EOP и какие функции доступны в EOP.

## <a name="how-eop-works"></a>Как работает EOP

Чтобы понять, как работает EOP, будет полезным взглянуть, как эта служба обрабатывает входящую электронную почту.

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="Графические сообщения электронной почты из Интернета или отзывов клиентов, проходящие в EOP и через подключение, анти-вредоносные программы, фильтрацию правил и политики почтовых процессов и фильтрацию контента до вынесения вердикта нежелательной почты или карантина, или доставки конечной почты пользователей.":::

1. При входящих сообщениях EOP оно сначала проходит фильтрацию подключения, которая проверяет репутацию отправитель. Большинство нежелательной почты останавливаются на этом этапе и отклоняется EOP. Дополнительные сведения см. в статье [Настройка фильтрации подключений](configure-the-connection-filter-policy.md).

2. Затем сообщение проверяется на вредоносные программы. Если вредоносные программы находятся в сообщении или вложении(ы), сообщение будет отправляться в хранилище только карантина администратора. Дополнительные информацию о защите от вредоносных программ см. в этой программе [в EOP.](anti-malware-protection.md)

3. Сообщение продолжается с помощью фильтрации политик, где оно оценивается с помощью любых созданных правил потока почты (также известных как правила транспорта). Например, правило может отправлять уведомление руководителю, когда сообщение поступает от конкретного отправитель.

   В локальной организации с Exchange Enterprise cal с лицензиями services проверки предотвращения потери данных [(DLP)](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention) в EOP также происходят на этом этапе.

4. Сообщение передается через фильтрацию контента (анти-нежелательной почты и подмены), где вредные сообщения идентифицированы как нежелательной почты, высокой уверенности в спаме, фишинге, фишинге с высоким уровнем доверия или массовом (политиках защиты от нежелательной почты) или спуфинге (параметры подмены в политиках защиты от фишинга). Вы можете настроить действие для принятия сообщения на основе вердикта фильтрации (карантин, переход в папку нежелательной почты и т.д.). Дополнительные сведения см. в [перенастройке](configure-your-spam-filter-policies.md) политик защиты от нежелательной почты и настройка политик защиты от фишинга [в EOP.](configure-anti-phishing-policies-eop.md)

Получателям доставляется сообщение, которое успешно передает все эти уровни защиты.

Дополнительные сведения см. в [сообщении Order и приоритете защиты электронной почты.](how-policies-and-protections-are-combined.md)

### <a name="eop-datacenters"></a>Центры обработки данных службы EOP

Служба EOP работает во всемирной сети центров данных, которые предназначены для обеспечения лучшей доступности. Например, если центр данных недоступен, сообщения электронной почты автоматически направляются в другой центр данных без остановки работы службы. Серверы каждого центра обработки данных принимают сообщения от вашего имени, обеспечивая уровень разделения между организацией и Интернетом, тем самым снижая нагрузку на серверы. Благодаря этой высокой доступности сети корпорация Майкрософт может гарантировать, что электронная почта достигнет вашей организации в установленные сроки.

Служба EOP выполняет балансировку нагрузки между центрами обработки данных, но только в пределах одного региона. Если ваша система настроена в одном регионе, все ваши сообщения будут обрабатываться с использованием маршрутизации для этого региона. В следующем списке показано, как региональная маршрутизация почты работает для центров обработки данных EOP:

- В Европе, на Ближнем Востоке и в Африке (регион EMEA) все почтовые ящики Exchange Online находятся в центрах обработки данных региона EMEA, а все сообщения направляются через центры обработки данных EMEA для фильтрации с помощью EOP.
- В Asia-Pacific (APAC) все почтовые ящики Exchange Online в центрах обработки данных APAC, и в настоящее время сообщения перенацелены через центр обработки данных APAC для фильтрации EOP.
- В Северной и Южной Америке службы распространяются в следующих местах:
  - Южная Америка: Exchange Online почтовые ящики расположены в центрах обработки данных в Бразилии и Чили. Все сообщения проходят через локальные центра обработки данных для фильтрации EOP. Карантинные сообщения хранятся в центре обработки данных, где расположен клиент.
  - Канада: Exchange Online почтовые ящики находятся в центрах обработки данных в Канаде. Все сообщения проходят через локальные центра обработки данных для фильтрации EOP. Карантинные сообщения хранятся в центре обработки данных, где расположен клиент.
  - СОЕДИНЕННЫЕ Штаты: Exchange Online почтовые ящики находятся в центрах обработки данных США. Все сообщения проходят через локальные центра обработки данных для фильтрации EOP. Карантинные сообщения хранятся в центре обработки данных, где расположен клиент.
- Для облака сообщества государственных учреждений США (GCC) все почтовые ящики Exchange Online находятся в центрах обработки данных в США, а все сообщения направляются через центры обработки данных в США для фильтрации с помощью EOP.

### <a name="eop-features"></a>Функции EOP

В этом разделе представлен краткий обзор основных функций, доступных в EOP.

Сведения о требованиях, важных ограничениях и доступности функций во всех планах подписки на EOP см. в Exchange Online Protection [службы.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

**Примечания**:

- Служба EOP использует несколько списков блокировок URL-адресов, которые помогают обнаруживать известные вредоносные ссылки в сообщениях.
- EOP использует обширный список доменов, которые, как известно, отправляют спам.
- EOP использует несколько систем защиты от вредоносных программ, которые помогают автоматически защищать наших клиентов во все времена.
- EOP проверяет активную полезной нагрузки в теле сообщения и все вложения сообщений для вредоносных программ.
- Рекомендуемые значения для политик защиты см. в рекомендациях для EOP и [Microsoft Defender для Office 365 безопасности.](recommended-settings-for-eop-and-office365.md)
- Краткие инструкции по настройке политик защиты см. в обзоре [Protect against threats.](protect-against-threats.md)

<br>

****
|Функция|Комментарии|
|---|---|
|**Protection**||
|Функции защиты от вредоносных программ|[Защита от вредоносных программ в EOP](anti-malware-protection.md) <p> [Вопросы и ответы по защите от вредоносных программ](anti-malware-protection-faq-eop.yml) <p> [Настройка политик по борьбе с вредоносными программами в EOP](configure-anti-malware-policies.md)|
|Входящий анти-спам|[Защита от нежелательной почты в EOP](anti-spam-protection.md) <p> [Вопросы и ответы по защите от нежелательной почты](anti-spam-protection-faq.yml) <p> [Настройка политик защиты от спама в EOP](configure-your-spam-filter-policies.md)|
|Исходящие анти-нежелательной почты|[Исходящие средства защиты от нежелательной почты в EOP](outbound-spam-controls.md) <p> [Настройка фильтрации исходящие нежелательной почты в EOP](configure-the-outbound-spam-policy.md) <p> [Управление автоматической внешней отправкой электронной почты в Microsoft 365](external-email-forwarding.md)|
|Фильтрация подключения|[Настройка фильтрации подключений](configure-the-connection-filter-policy.md)|
|Anti-phishing|[Политики защиты от фишинга в Microsoft 365](set-up-anti-phishing-policies.md) <p> [Настройка политик защиты от фишинга в EOP](configure-anti-phishing-policies-eop.md)|
|Защита от спуфинга|[Spoof intelligence insight in EOP](learn-about-spoof-intelligence.md) <p> [Управление списком разрешенных и запрещенных клиентов](tenant-allow-block-list.md)|
|Автоматическая очистка нулевого часа (ZAP) для доставленных вредоносных программ, спама и фишинговых сообщений|[ZAP в Exchange Online](zero-hour-auto-purge.md)|
|Готовые политики безопасности|[Предустановленные политики безопасности в EOP и Microsoft Defender для Office 365](preset-security-policies.md) <p> [Анализатор конфигурации для политик защиты в EOP и Microsoft Defender для Office 365](configuration-analyzer-for-security-policies.md)|
|Список разрешить/заблокировать клиента|[Управление списком разрешенных и запрещенных клиентов](tenant-allow-block-list.md)|
|Блокировка списков отправителей сообщений|[Создание заблокированных списков отправитель в EOP](create-block-sender-lists-in-office-365.md)|
|Разрешить списки отправителей сообщений|[Создание безопасных списков отправитель в EOP](create-safe-sender-lists-in-office-365.md)|
|Directory Based Edge Blocking (DBEB)|[Use Directory Based Edge Blocking to reject messages sent to invalid recipients](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) (Использование пограничной блокировки на основе каталогов для отклонения сообщений, отправленных недопустимым получателям)|
|**Карантин и отправка**||
|Отправка администратора|[Отправка администратора для отправки подозрительных спама, фишинга, URL-адресов и файлов в Корпорацию Майкрософт](admin-submission.md)|
|Отправки пользователей (настраиваемый почтовый ящик)|[Политика отправки пользователей](user-submission.md)|
|Карантин — администраторы|[Управление сообщениями и файлами, помещенными в карантин, в качестве администратора в EOP](manage-quarantined-messages-and-files.md) <p> [FaQ сообщений в карантине](quarantine-faq.yml) <p> [Передача информации о сообщениях и файлах в корпорацию Майкрософт](report-junk-email-messages-to-microsoft.md) <p> [Заголовки сообщений о защите от нежелательной почты в Microsoft 365](anti-spam-message-headers.md) <p> Вы можете проанализировать заглавные сообщения карантинов сообщений с помощью анализатора [загона сообщений по .](https://mha.azurewebsites.net/)|
|Карантин — конечные пользователи|[Поиск и выпуск сообщений на карантине в EOP](find-and-release-quarantined-messages-as-a-user.md) <p> [Использование уведомлений о нежелательной почте пользователей для выпуска и сообщения с карантином](use-spam-notifications-to-release-and-report-quarantined-messages.md)|
|**Поток обработки почты**||
|Правила потока обработки почты|[Правила потока обработки почты (правила транспорта) в Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) <p> [Условия и исключения (предикаты) правил для потока обработки почты в Exchange Online](/exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions) <p> [Действия правил потока почты в Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions) <p> [Правила потока обработки почты в Exchange Online](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules) <p> [Процедуры правил потока почты в Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-procedures)|
|Обслуживаемые домены|[Управление обслуживаемыми доменами в Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)|
|Соединители|[Настройка потока почты с помощью соединители в Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)|
|Улучшенная фильтрация соединителей|[Улучшенная фильтрация соединители в Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)|
|**Мониторинг**||
|Трассировка сообщений|[Трассировка сообщений](message-trace-scc.md) <p> [Трассировка сообщений в Exchange центре администрирования](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)|
|Отчеты & совместной работы по электронной почте|[Просмотр отчетов о безопасности электронной почты](view-email-security-reports.md)|
|Отчеты о потоке почты|[Просмотр правил потока обработки почты](view-mail-flow-reports.md) <p> [Отчеты о потоке почты в Exchange центре администрирования](/exchange/monitoring/mail-flow-reports/mail-flow-reports)|
|Сведения о потоке почты|[Сведения о потоке почты](mail-flow-insights-v2.md) <p> [Сведения о потоке почты в Exchange центре администрирования](/exchange/monitoring/mail-flow-insights/mail-flow-insights)|
|Отчеты аудита|[Аудит отчетов в центре Exchange администрирования](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports)|
|Политики оповещений|[Политики оповещений](../../compliance/alert-policies.md)|
|**Соглашения об уровне обслуживания (SLA) и поддержка**||
|Соглашение об уровне обслуживания относительно эффективности защиты от нежелательной почты|\> 99%|
|Соглашение об уровне обслуживания в отношении количества ложных срабатываний|\< 1:250,000|
|Соглашение об уровне обслуживания в отношении обнаружения и блокировки вирусов|100 % известных вирусов|
|Соглашение об уровне обслуживания в отношении ежемесячного времени работы|99,999 %|
|Поддержка по телефону и через Интернет предоставляется 24 часа в сутки семь дней в неделю.|[Справка и поддержка для EOP](help-and-support-for-eop.md).|
|**Другие функции**||
|Глобальная сеть геодублированных серверов|Служба EOP работает во всемирной сети центров данных, которые предназначены для обеспечения лучшей доступности. Дополнительные сведения см. в разделе Центр обработки данных [EOP](#eop-datacenters) в этой статье.|
|Организация очередей сообщений, если локальный сервер не может принимать почту|Сообщения в отсрочке остаются в очередях в течение одного дня. Попытки повторной отправки сообщений зависят от ошибки, полученной от почтовой системы получателя. Повторные попытки в среднем выполняются каждые 5 минут. Дополнительные сведения см. в [faq faq](eop-queued-deferred-and-bounced-messages-faq.yml)сообщений eOP в очереди, отложенных и отскочил.|
|шифрование сообщений Office 365 в качестве надстройки|Дополнительные сведения см. в статье [Шифрование в Office 365](../../compliance/encryption.md).    |
|||
