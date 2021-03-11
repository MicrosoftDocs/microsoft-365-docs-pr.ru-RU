---
title: Безопасность Office 365, Microsoft Defender для Office 365, EOP, MSDO
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
description: Безопасность в Office 365, от EOP до Defender для Office 365 Plans 1 и 2, Standard vs. Strict security configurations и другие. Поймите, что у вас есть, и как защитить свои свойства.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e1c6e768098cd59892c2572fb52497c873aef1a3
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/10/2021
ms.locfileid: "50711944"
---
# <a name="office-365-security-overview"></a>Обзор безопасности Office 365

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](office-365-atp.md)


В этой статье вы познакомите вас с новыми свойствами безопасности в облаке. Независимо от того, являетесь ли вы частью Центра операций безопасности, вы являетесь администратором безопасности, новым для пространства, или хотите обновить, давайте начнем работу.

> [!CAUTION]
> Если вы используете **Outlook.com,** Microsoft **365 Family** или **Microsoft 365 Personal** и  вам нужна информация о безопасных ссылках или безопасных вложениях, нажмите эту ссылку: Расширенные Outlook.com безопасности для подписчиков Microsoft [365](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).  

## <a name="office-365-security-spelled-out"></a>Безопасность Office 365

Каждая подписка Office 365 поставляется с возможностями безопасности. Цели и действия, которые можно принять, зависят от фокуса этих различных подписок. В службе безопасности Office 365 три основные службы безопасности (или продукты) привязаны к типу подписки:

1. Exchange Online Protection (EOP)
1. Microsoft Defender for Office 365 Plan 1 (Defender for Office P1)
1. Microsoft Defender for Office 365 Plan 2 (Defender for Office P2)

> [!NOTE]
> Если вы приобрели подписку и вам необходимо сейчас выкатить функции *безопасности,* перескочить к шагам в статье [Protect Against Threats.](protect-against-threats.md) Если вы не знаете свою подписку и хотите узнать лицензию перед началом работы, просмотрите > Ваши продукты в центре администрирования [Microsoft 365.](https://admin.microsoft.com/AdminPortal/#/homepage)

Безопасность Office 365 строится на основных средствах защиты, предлагаемых EOP. EOP присутствует в любой подписке, где можно найти почтовые ящики Exchange Online (помните, что все продукты безопасности, о которых здесь идет речь, являются облачными).

Вы можете привыкнуть к тому, что эти три компонента обсуждаются таким образом:

|EOP|Microsoft Defender для Office 365 P1|Microsoft Defender для Office 365 P2|
|---|---|---|
|Предотвращает широкомасштабные, основанные на томе, известные атаки.|Защищает электронную почту и совместную работу от вредоносных программ, фишинга и бизнес-сообщений.|Добавляет расследование после нарушения, охоту и ответ, а также автоматизацию и моделирование (для обучения).|
|

Но с точки зрения архитектуры давайте начнем с того, что каждый элемент будет совокупным с точки зрения безопасности, каждый из которых имеет особое значение для безопасности. Подробнее:

<!--:::image type="content" source="../../media/tp-EOPATPStack.PNG" alt-text="Placeholder graphic":::-->

:::image type="content" source="../../media/tp_GraphicEOPATPP1P2_2.png" alt-text="EOP и Microsoft Defender для Office 365 и их отношения друг с другом с акцентом на службу, в том числе примечание для проверки подлинности электронной почты.":::

Хотя каждая из этих служб подчеркивает цель из числа Protect, Detect, Investigate и Respond,***** все _ службы могут выполнять *___* любые * целей по защите, обнаружению, исследованию и реагированию.

Ядром безопасности Office 365 является защита EOP. Microsoft Defender для Office 365 P1 содержит EOP в нем. Defender for Office 365 P2 содержит P1 и EOP. Структура накопительная. Поэтому при настройке этого продукта следует начинать с EOP и работать с Defender для Office 365.

Несмотря на то, что конфигурация проверки подлинности электронной почты имеет место в общедоступных DNS, важно настроить эту функцию, чтобы защититься от подмены. *Если у вас есть EOP,* ***необходимо настроить [проверку подлинности электронной почты.](email-validation-and-authentication.md)***

Если у вас есть Office 365 E3 или ниже, у вас есть EOP, но с возможностью купить автономный защитник для Office 365 P1 через обновление. Если у вас есть Office 365 E5, у вас уже есть Defender для Office 365 P2.

> [!TIP]
> Если ваша подписка не является Office 365 E3 или E5, вы можете проверить, есть ли у вас возможность обновления до Microsoft Defender для Office 365 P1. Если вам [интересно,](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids) на этой веб-странице перечислены подписи, подходящие для обновления Microsoft Defender для Office 365 P1 (проверьте конец страницы для печати).

## <a name="the-office-365-security-ladder-from-eop-to-microsoft-defender-for-office-365"></a>Лестница безопасности Office 365 от EOP до Microsoft Defender для Office 365

![EOP и Microsoft Defender для Office 365 и их внимание к безопасности, начиная с Protect and Detect to Investigate and Respond. Конфигурация проверки подлинности электронной почты (по крайней мере DKIM и DMARC) должна быть настроена для EOP и up.](../../media/tp_EOPATPP1P2Take6.gif#lightbox)

> [!IMPORTANT]
> Узнайте подробности на этих страницах: [Exchange Online Protection](exchange-online-protection-overview.md)и Defender для Office [365.](office-365-atp.md)

Что делает добавление планов Microsoft Defender для Office 365 преимуществом для чистого управления угрозами EOP, на первый взгляд сказать сложно. Чтобы разобраться, подходит ли путь обновления для организации, рассмотрим возможности каждого продукта, когда речь заходит о:

- предотвращение и обнаружение угроз
- исследование
- реагирование

начиная с **Exchange Online Protection:**
<p>

|Предотвращение/обнаружение|Исследование|Реагирование|
|---|---|---|
|Технологии включают в себя:<ul><li>уверенности</li><li>фишинг</li><li>вредоносные программы</li><li>массовая почта</li><li>подмена сведений</li><li>Обнаружение обезличения</li><li>Карантин администратора</li><li>Отправки администратором и пользователем ложных срабатыва-</li><li>Разрешить/заблокировать URL-адреса и файлы</li><li>Отчеты</li></u1>|<li>Поиск в журнале аудита</li><li>Трассировка сообщений</li>|<li>Авточистка с нулевой часовой отметкой (ZAP)</li><li>Уточнение и тестирование списков разрешить и заблокировать</li>|
|

Если вы хотите копать в EOP, **[перейти к этой статье](exchange-online-protection-overview.md)**.

Поскольку эти продукты являются накопительными, если вы оцените Microsoft Defender для Office 365 P1 и решите подписаться на него, вы добавим эти возможности.

Выгоды **с Defender для Office 365, Plan 1** (на сегодняшний день):
<p>

|Предотвращение/обнаружение|Исследование|Реагирование|
|---|---|---|
|Технологии включают все в EOP плюс:<u1><li>Безопасные вложения</li><li>Безопасные ссылки<li>Защита Microsoft Defender для Office 365 для рабочих нагрузок (например. SharePoint Online, Teams, OneDrive для бизнеса)</li><li>Защита во время щелчка мыши в электронной почте, клиентах Office и teams</li><li>защита от фишинга в Defender для Office 365</li><li>Защита от обезличения пользователя и домена</li><li>Оповещений и API интеграции SIEM для оповещений</li>|<li>API интеграции SIEM для обнаружения</li><li>**Средство обнаружения в режиме реального времени**</li><li>Трассировка URL-адреса</li>|<li>Такой же</li></u1>

Таким образом, Microsoft Defender для Office 365 P1 расширяется на стороне ***prevention** _ дома и добавляет дополнительные формы _обнаружения_ _* **.

Microsoft Defender для Office 365 P1 также добавляет обнаружения в режиме реального времени **для** расследований. Имя этого средства охоты на угрозы является смелым, так как наличие четкого средства, чтобы узнать, что у вас есть Defender для Office 365 P1.  Он не появляется в Defender для Office 365 P2.

Выгоды **с Defender для Office 365, Plan 2** (на сегодняшний день):
<p>

|Предотвращение/обнаружение|Исследование|Реагирование|
|---|---|---|
|Технологии включают все в EOP и Microsoft Defender для Office 365 P1 плюс:<u1><li>Такой же</li>|<li>**Обозреватель угроз**</li><li>Журналы учета угроз</li><li>Представления кампании</li>|<li>Автоматизированное исследование и реагирование (AIR)</li><li>AIR from Threat Explorer</li><li>AIR для скомпрометированных пользователей</li><li>API интеграции SIEM для автоматизированных расследований</li>

Таким образом, Microsoft Defender для Office 365 P2 расширяется на стороне исследования и ответа дома и добавляет новую силу охоты.  Автоматизация.

В Microsoft Defender для Office 365 P2 основное средство охоты называется **Explorer** угроз, а не обнаружение в режиме реального времени. Если вы видите Обозреватель угроз при переходе в центр безопасности, вы в Microsoft Defender для Office 365 P2.

Чтобы получить сведения о Microsoft Defender для Office 365 P1 и P2, **[переперейти к этой статье](office-365-atp.md)**.

> [!TIP]
> EOP и Microsoft Defender для Office 365 также отличаются от конечных пользователей. В EOP и Defender для Office 365 P1 основное внимание уделяется повышению осведомленности, поэтому эти две службы включают надстройку Report *Message Outlook,* чтобы пользователи могли сообщать о сообщениях электронной почты, которые они считают подозрительными, для дальнейшего анализа. <p> В Defender for Office 365 P2 (который содержит все в EOP и P1) фокус смещается к дальнейшей  подготовке для конечных пользователей, поэтому Центр операций безопасности имеет доступ к мощному средству Симулятор угроз и метрике конечных пользователей, которые он предоставляет. 

## <a name="microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet"></a>Microsoft Defender для Office 365 Plan 1 vs. Plan 2 cheat sheet

Эта быстрая ссылка поможет вам понять, какие возможности есть с каждой подпиской Microsoft Defender для Office 365. В сочетании с вашими знаниями об особенностях EOP он может помочь бизнес-органам, принимающим решения, определить, что Microsoft Defender для Office 365 лучше всего для их потребностей.

|Defender for Office 365 Plan 1|Defender for Office 365 Plan 2|
|---|---|
|Конфигурация, защита и возможности обнаружения: <ul><li>[Безопасные вложения](atp-safe-attachments.md)</li><li>[Безопасные ссылки](atp-safe-links.md)</li><li>[Безопасные вложения для SharePoint, OneDrive и Microsoft Teams](atp-for-spo-odb-and-teams.md)</li><li>[Защита от фишинга в Defender для Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[Обнаружение в режиме реального времени](threat-explorer.md)</li></ul>|Возможности Defender для Office 365 Plan 1 <p> --- плюс --- <p> Автоматизация, исследование, исправления и возможности образования. <ul><li>[Трекеры угроз](threat-trackers.md)</li><li>[Обозреватель угроз](threat-explorer.md)</li><li>[Автоматизированный анализ угроз и реагирование на них](office-365-air.md)</li><li>[Эмулятор атак](attack-simulator.md)</li></ul>|
|

- Microsoft Defender для Office 365 Plan 2 включен в Office 365 E5, Office 365 A5 и Microsoft 365 E5.

- Microsoft Defender для Office 365 с планом 1 входит в состав Microsoft 365 бизнес премиум.

- Microsoft Defender для Office 365 Plan 1 и Defender for Office 365 Plan 2 доступны в качестве надстройки для определенных подписок. Дополнительные дополнительные ссылки можно найти в планах [Microsoft Defender для Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)

- Функция [безопасных документов](safe-docs.md) доступна только пользователям с лицензией Microsoft 365 E5 или Безопасность Microsoft 365 E5 (не предусмотренные планами Microsoft Defender для Office 365).

- Если текущая подписка не включает Microsoft Defender для Office 365 и вы этого [хотите,](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html)свяжитесь с продажами, чтобы начать пробную проверку, и узнайте, как Microsoft Defender для Office 365 может работать в вашей организации.

> [!TIP]
> ***Совет инсайдера** _. Вы можете использовать docs.microsoft.com содержимого, чтобы узнать об EOP и Microsoft Defender для Office 365. Перейдите на эту страницу, обзор [безопасности Office 365,](index.md)и вы заметите, что таблица организации контента в боковой панели. Она начинается с развертывания (в том числе миграции), а затем продолжается в области профилактики, обнаружения, расследования и реагирования. <p> Эта структура разделена таким образом, чтобы разделы *_Security Administration** следуют **темы Операции безопасности.** Если вы новый член любой роли задания, используйте ссылку в этом совете, и ваши знания о таблице содержимого, чтобы помочь узнать пространство. Не забудьте использовать *ссылки на отзывы* *и статьи о ставках* по мере их использования. Отзывы помогают нам улучшить то, что мы предлагаем вам.

## <a name="where-to-go-next"></a>Куда идти дальше

Если вы администратор безопасности, вам может потребоваться настроить DKIM или DMARC для вашей почты. Возможно, вам нужно вывести предуговоки безопасности "Strict" для приоритетных пользователей или найти новые возможности в продукте. Если вы в службе безопасности, вам может потребоваться использовать обнаружения в режиме реального времени или Обозреватель угроз для расследования и реагирования или обучения обнаружения конечных пользователей с помощью симулятора атаки. В любом случае, вот некоторые дополнительные рекомендации по следующим рекомендациям.

[Проверка подлинности электронной почты, включая SPF, DKIM и DMARC (со ссылками на настройку всех трех)](email-validation-and-authentication.md)

[См. конкретные рекомендуемые "золотые" конфигурии](recommended-settings-for-eop-and-office365-atp.md) и используйте их рекомендуемые пресеты для [быстрой](preset-security-policies.md) настройки политик безопасности

Наверстать [упущенное в Microsoft Defender для Office 365 (включая разработки EOP)](whats-new-in-office-365-atp.md)

[Использование обнаружения обозревателя угроз или обнаружения в режиме реального времени](threat-explorer.md)

Использование [симулятора атак в Microsoft Defender для Office 365](attack-simulator.md)
