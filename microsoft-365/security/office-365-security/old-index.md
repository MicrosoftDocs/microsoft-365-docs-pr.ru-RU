---
title: Office 365 Обзор безопасности, Microsoft Defender для Office 365, EOP, MSDO
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 08/13/2020
audience: Admin
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Безопасность в Office 365, от EOP до Defender для Планов 1 и 2 Office 365, стандартные и строгие конфигурации безопасности и т.д. Узнайте, что у вас есть, и узнайте, как защитить свои свойства.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8040a6b7758e271d68af872bc2acf9ebac3af9d4
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926491"
---
# <a name="office-365-security"></a>Безопасность Office 365


**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](defender-for-office-365.md)


Эта статья познакомит вас с новыми свойствами безопасности в облаке. Независимо от того, являетесь ли вы частью Центра управления безопасностью, новым администратором безопасности или хотите обновить что-то, давайте приступим.

> [!CAUTION]
> Если вы используете **Outlook.com**, **Microsoft 365 для семьи** или **Microsoft 365 персональный**, и вам необходимы сведения о *Безопасных ссылках* или *Безопасных вложениях*, ***щелкните эту ссылку***: [Расширенные возможности безопасности Outlook.com для подписчиков Microsoft 365](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).

## <a name="office-365-security-spelled-out"></a>Безопасность Office 365 в деталях

Каждая подписка на Office 365 поставляется с возможностями безопасности. Цели и действия, которые можно предпринять, зависят от фокуса этих различных подписок. В системе безопасности Office 365 есть три основных службы (или продукта) безопасности, привязанные к типу подписки:

1. Exchange Online Protection (EOP)
1. Microsoft Defender для Office 365 План 1 (Defender для Office P1)
1. Microsoft Defender для Office 365 План 2 (Defender для Office P2)

> [!NOTE]
> Если вы приобрели подписку и вам необходимо развернуть функции безопасности *прямо сейчас*, перейдите к действиям, описанным в статье [Защита от угроз](protect-against-threats.md). Если вы только приобрели подписку и хотели бы узнать возможности вашей лицензии перед началом, перейдите в раздел "Выставление счетов" > "Ваши продукты" в [Центре администрирования Microsoft 365](https://admin.microsoft.com/AdminPortal/#/homepage).

Безопасность Office 365 основана на основных средствах защиты, предлагаемых EOP. EOP присутствует в любой подписке, где можно найти почтовые ящики Exchange Online (помните, что все обсуждаемые здесь продукты безопасности являются облачными).

Возможно, вы привыкли видеть эти три компонента, рассмотренные таким образом:

|EOP|Microsoft Defender для Office 365 P1|Microsoft Defender для Office 365 P2|
|---|---|---|
|Предотвращает широкомасштабные известные атаки на основе объема.|Защищает электронную почту и совместную работу от вредоносных программ нулевого дня, фишинга и компрометации корпоративной электронной почты.|Добавляет исследование после взлома, поиск и реагирование, а также автоматизацию и симуляцию (для обучения).|
|

Но с точки зрения архитектуры, давайте начнем с рассмотрения каждой части как накопительных уровней безопасности, каждый из которых делает упор на безопасность. Подробнее об этом:

<!--:::image type="content" source="../../media/tp-EOPATPStack.PNG" alt-text="Placeholder graphic":::-->

:::image type="content" source="../../media/tp_GraphicEOPATPP1P2_2.png" alt-text="EOP и Microsoft Defender для Office 365 и их взаимосвязь друг с другом с акцентом на службе, включая примечание для проверки подлинности электронной почты.":::

Хотя каждая из этих служб подчеркивает цель из числа "Защита, обнаружение, расследование и реагирование", ***все** _ службы могут выполнять _ *_любую_** из целей защиты, обнаружения, расследования и реагирования.

Ядром безопасности Office 365 является защита EOP. Microsoft Defender для Office 365 P1 содержит EOP. Defender для Office 365 План 2 содержит P1 и EOP. Структура является накопительной. Поэтому при настройке этого продукта следует начинать с EOP и работать с Defender для Office 365.

Хотя настройка проверки подлинности электронной почты происходит в общедоступных DNS, важно настроить эту функцию для защиты от спуфинга. *Если у вас есть EOP,* ***необходимо [настроить проверку подлинности электронной почты](email-validation-and-authentication.md)***.

Если у вас есть Office 365 E3 или ниже, у вас есть EOP, но с возможностью приобрести автономный Defender для Office 365 P1 путем обновления. Если у вас есть Office 365 E5, у вас уже есть Defender для Office 365 P2.

> [!TIP]
> Если ваша подписка не является ни Office 365 E3, ни E5, вы все равно можете проверить, есть ли у вас возможность обновить до Microsoft Defender для Office 365 P1. Если вас это интересует, [на этой веб-странице](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids) перечислены подписки, подходящие для обновления Microsoft Defender для Office 365 P1 (подробнее см. в конце страницы).

## <a name="the-office-365-security-ladder-from-eop-to-microsoft-defender-for-office-365"></a>Лестница Безопасности Office 365 от EOP до Microsoft Defender для Office 365

![EOP и Microsoft Defender для Office 365 и их акцент на безопасности, начиная с защиты и обнаружения и заканчивая исследованием и реагированием. Конфигурация проверки подлинности электронной почты (как минимум DKIM и DMARC) должна быть настроена для EOP и выше.](../../media/tp_EOPATPP1P2Take6.gif#lightbox)

> [!IMPORTANT]
> Дополнительные сведения см. на этих страницах: [Exchange Online Protection](exchange-online-protection-overview.md) и [Defender для Office 365](defender-for-office-365.md).

С первого взгляда сложно сказать, что делает добавление Microsoft Defender для планов Office 365 преимуществом по сравнению с чистым управлением угрозами EOP. Чтобы понять, подходит ли вариант обновления для вашей организации, давайте рассмотрим возможности каждого продукта, когда речь идет о:

- предотвращении и обнаружении угроз
- изучении
- реагировании

начиная с **Exchange Online Protection**:
<p>

|Предотвращение/Обнаружение|Исследование|Реагирование|
|---|---|---|
|К технологиям относятся:<ul><li>спам</li><li>фишинг</li><li>вредоносная программа</li><li>массовая рассылка</li><li>аналитика спуфинга</li><li>обнаружение олицетворения</li><li>Карантин администратора</li><li>Отправка ложных срабатываний и ложных отрицаний администратором и пользователями</li><li>Разрешить или заблокировать для URL-адресов и файлов</li><li>Отчеты</li></u1>|<li>Поиск в журнале аудита</li><li>Трассировка сообщений</li>|<li>Автоматическая очистка (ZAP)</li><li>Уточнение и тестирование списков "Разрешить" и "Заблокировать"</li>|
|

Если вы хотите углубиться в EOP, **[перейдите к этой статье](exchange-online-protection-overview.md)**.

Так как эти продукты являются накопительными, если вы оцените Microsoft Defender для Office 365 P1 и решите подписаться на него, вы добавите эти возможности.

Преимущества **Defender для Office 365, план 1** (на данный момент):
<p>

|Предотвращение/Обнаружение|Исследование|Реагирование|
|---|---|---|
|Технологии включают все, что включено в EOP, а также:<u1><li>Безопасные вложения</li><li>Безопасные ссылки<li>Защита Microsoft Defender для Office 365 для рабочих нагрузок (например, SharePoint Online, Teams, OneDrive для бизнеса)</li><li>Защита во время щелчка в электронной почте, клиентах Office и Teams</li><li>защита от фишинга в Defender для Office 365</li><li>Защита от олицетворения пользователя и домена</li><li>Оповещения и API интеграции с SIEM для оповещений</li>|<li>API интеграции с SIEM для обнаружения</li><li>**Средство обнаружения в реальном времени**</li><li>Трассировка URL-адреса</li>|<li>Одинаковое</li></u1>

Таким образом, Microsoft Defender для Office 365 P1 расширяет возможности ***предотвращения** _ и добавляет дополнительные формы _*_обнаружения_**.

Microsoft Defender для Office 365 P1 также **добавляет обнаружение в реальном времени** для расследований. Название этого средства для поиска угроз выделено жирным шрифтом, потому что его наличие дает четкое *представление* о том, что у вас есть Defender для Office 365 P1. Оно не появляется в Defender для Office 365 P2.

Преимущества **Defender для Office 365, план 2** (на данный момент):
<p>

|Предотвращение/Обнаружение|Исследование|Реагирование|
|---|---|---|
|Технологии включают в себя все, что есть в EOP и Microsoft Defender для Office 365 P1, а также:<u1><li>Одинаковое</li>|<li>**Обозреватель угроз**</li><li>Журналы учета угроз</li><li>Представления кампании</li>|<li>Автоматическое исследование и реагирование (AIR)</li><li>AIR из обозревателя угроз</li><li>AIR для скомпрометированных пользователей</li><li>API интеграции с SIEM для автоматических исследований</li>

Таким образом, Microsoft Defender для Office 365 P2 расширяет возможности ***исследования и реагирования*** и добавляет новые возможности для охоты на угрозы. Автоматизация.

В Microsoft Defender для Office 365 P2 основное средство охоты на угрозы называется **обозревателем угроз**, а не обнаружением в реальном времени. Если при переходе в Центр безопасности вы видите обозреватель угроз, значит, вы находитесь в Microsoft Defender для Office 365 P2.

Чтобы получить сведения о Microsoft Defender для Office 365 P1 и P2, **[перейдите к этой статье](defender-for-office-365.md)**.

> [!TIP]
> EOP и Microsoft Defender для Office 365 также отличаются для конечных пользователей. В EOP и Defender для Office 365 P1 основное внимание уделяется *информированию*, поэтому эти две службы включают *надстройку Outlook "Пожаловаться на сообщение"*, чтобы пользователи могли сообщать о сообщениях электронной почты, которые они считают подозрительными, для дальнейшего анализа. <p> В Defender для Office 365 P2 (который содержит все, что есть в EOP и P1) фокус смещается на *дальнейшее обучение* для конечных пользователей, и поэтому Центр управления безопасностью имеет доступ к мощному средству *симулятора угроз*, а также метрикам конечных пользователей, которые он предоставляет.

## <a name="microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet"></a>Памятка по использованию Защитника Microsoft для Office 365 План 1 и План 2

Этот краткий справочник поможет вам понять, какие возможности входят в каждую подписку Microsoft Defender для Office 365. В сочетании с вашими знаниями о функциях EOP это может помочь людям, принимающим бизнес-решения, определить, какой Microsoft Defender для Office 365 лучше всего подходит для их нужд.

|Defender для Office 365 (план 1)|Defender для Office 365 (план 2)|
|---|---|
|Конфигурация, защита и возможности обнаружения: <ul><li>[Безопасные вложения](safe-attachments.md)</li><li>[Безопасные ссылки](safe-links.md)</li><li>[Безопасные вложения для SharePoint, OneDrive и Microsoft Teams](mdo-for-spo-odb-and-teams.md)</li><li>[Защита от фишинга в Defender для Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[Обнаружение в режиме реального времени](threat-explorer.md)</li></ul>|Возможности Defender для Office 365 (план 1) <p> --- плюс --- <p> Автоматизация, исследование, исправления и возможности образования. <ul><li>[Трекеры угроз](threat-trackers.md)</li><li>[Обозреватель угроз](threat-explorer.md)</li><li>[Автоматизированный анализ угроз и реагирование на них](office-365-air.md)</li><li>[Эмулятор атак](attack-simulator.md)</li></ul>|
|

- Пакет Microsoft Defender для Office 365 с планом 2 входит в состав Office 365 E5, Office 365 A5 и Microsoft 365 E5.

- Microsoft Defender для Office 365 (план 1) входит в состав Microsoft 365 бизнес премиум.

- Microsoft Defender для Office 365 (план 1) и Defender для Office 365 (план 2) доступны как дополнение к некоторым подпискам. Дополнительные сведения см. в разделе [Доступность функций в планах Microsoft Defender для Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

- Функция [безопасных документов](safe-docs.md) доступна только пользователям с лицензией Microsoft 365 E5 или Безопасность Microsoft 365 E5 (не предусмотренные планами Microsoft Defender для Office 365).

- Если текущая подписка не включает в себя Microsoft Defender для Office 365, [обратитесь в отдел продаж для начала использования пробной версии](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html) и узнайте, как Microsoft Defender для Office 365 может работать в вашей организации.

> [!TIP]
> ***Совет Insider** _. Чтобы узнать об EOP и Microsoft Defender для Office 365, можно использовать содержание docs.microsoft.com. Вернитесь на страницу [Обзор безопасности Office 365](index.yml), и вы заметите организацию содержания на боковой панели. Он начинается с развертывания (включая миграцию), а затем продолжается предотвращением, обнаружением, расследованием и реагированием. <p> Эта структура разделена таким образом, чтобы за темами _ *Администрирование безопасности** следуют темы **Операции, связанные с обеспечением безопасности**. Если вы новый участник любой из ролей задания, воспользуйтесь ссылкой в этом совете и своими знаниями оглавления, чтобы изучить пространство. Не забудьте использовать *ссылки для отзывов* и *оценивать статьи* по ходу дела. Отзывы помогают нам улучшить то, что мы вам предлагаем.

## <a name="where-to-go-next"></a>Куда перейти дальше

Если вы являетесь администратором безопасности, вам может потребоваться настроить DKIM или DMARC для почты. Возможно, вы захотите развернуть "Строгие" предустановки безопасности для приоритетных пользователей или найти новые возможности в продукте. Или с помощью службы безопасности можно использовать обнаружение в реальном времени или Обозревателя угроз для расследования и реагирования, или обучить обнаружение конечных пользователей с помощью эмулятора атак. В любом случае, вот несколько дополнительных рекомендаций, на что смотреть дальше.

[Проверка подлинности электронной почты, включая SPF, DKIM и DMARC (со ссылками на настройку всех трех)](email-validation-and-authentication.md)

[Просмотрите конкретные рекомендуемые "золотые" конфигурации](recommended-settings-for-eop-and-office365.md) и [используйте их рекомендуемые предустановки для быстрой настройки политик безопасности](preset-security-policies.md)

Узнавайте о [новых возможностях Microsoft Defender для Office 365 (включая разработки EOP)](whats-new-in-defender-for-office-365.md)

[Использование обозревателя угроз или обнаружения угроз в режиме реального времени](threat-explorer.md)

Использование [эмулятора атак в Microsoft Defender для Office 365](attack-simulator.md)
