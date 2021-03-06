---
title: Этап 1. Анализ и анализ первого инцидента
description: Как проанализировать и приступить к анализу первого инцидента в Microsoft 365 Defender.
keywords: инциденты, оповещения, расследование, корреляция, атака, компьютеры, устройства, пользователи, удостоверения, удостоверения, почтовый ящик, электронная почта, 365, Microsoft, m365, реагирование на инциденты, кибератака
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 82e1d1b117fd8c68077a249a14f66b9915d517e9
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287775"
---
# <a name="step-1-triage-and-analyze-your-first-incident"></a>Этап 1. Анализ и анализ первого инцидента

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**
- Microsoft 365 Defender

Потратив некоторое время на создание, реализацию и поддержание мер безопасности в соответствии со стандартами организации, вы можете настроить решения безопасности, которые помогут быстро определить риски и угрозы безопасности. Microsoft 365 Defender позволяет обнаруживать, выявлять и расследовать инциденты с помощью единого стекла, где можно найти информацию, необходимую для принятия решений.

После обнаружения инцидента с безопасностью Microsoft 365 Defender подробные сведения, необходимые для определения или определения приоритетов инцидента или инцидентов над другими. После определения приоритетов аналитики могут сосредоточиться на расследовании случаев, назначенных им.

## <a name="detection-by-microsoft-365-defender"></a>Обнаружение по Microsoft 365 Defender

Microsoft 365 Defender получает оповещения и события с нескольких платформ безопасности Майкрософт в качестве источников обнаружения, чтобы создать целостную картину и контекст вредоносных действий. Это возможные источники обнаружения:

- [Microsoft Defender для конечной](../defender-endpoint/microsoft-defender-endpoint.md) точки — это обнаружение и нейтрализация атак на конечные точки (EDR), использующее антивирус Microsoft Defender, а также облачную передовую защиту от угроз с помощью microsoft Security Graph. Defender for Endpoint — это единая платформа для профилактической защиты, обнаружения нарушений, автоматического расследования и реагирования. Он защищает конечные точки от киберугроз, обнаруживает расширенные атаки и нарушения данных, автоматизирует инциденты с безопасностью и улучшает осанку безопасности.
- [Microsoft Defender for Identity](/defender-for-identity/what-is) — это облачное решение безопасности, использующее внутренние сигналы Active Directory Domain Services (AD DS) для выявления, обнаружения и расследования расширенных угроз, скомпрометированных удостоверений и вредоносных действий инсайдеров, направленных на организацию.
- [Microsoft Cloud App Security](/cloud-app-security/) в качестве привратника для брокерского доступа в режиме реального времени между корпоративными пользователями и облачными ресурсами, которые они используют, где бы ваши пользователи ни находились и независимо от используемого ими устройства.
- [Microsoft Defender для Office 365](../office-365-security/overview.md) вашей организации от вредоносных угроз в сообщениях электронной почты, ссылках (URL-адресах) и средствах совместной работы.
- [Центр безопасности Azure](/azure/security-center/security-center-introduction) — это единая система управления безопасностью инфраструктуры, которая укрепляет положение в области безопасности центров обработки данных и обеспечивает расширенные возможности защиты от угроз в гибридных рабочих нагрузках в облаке, а также на локальной основе.

В Microsoft 365 Defender случае [инциденты](incidents-overview.md) выявляются путем сопоставления оповещений из этих различных источников обнаружения. Вместо расходования ресурсов, натягив их вместе или разграничив несколько оповещений в соответствующих инцидентах, вы можете начать с очереди инцидента в Microsoft 365 Defender сразу. Это позволяет эффективно порядок проверки инцидентов в конечных точках, удостоверениях, электронной почте и приложениях, а также уменьшить ущерб от атаки.

## <a name="triage-your-incidents"></a>Проверка инцидентов

Реагирование на Microsoft 365 Defender начинается после того, как вы обнажайте список инцидентов с помощью рекомендуемого метода приоритетов вашей организации. Определение уровня важности или срочности для инцидентов, которые затем определяют порядок, в котором они будут расследоваться.

Полезное руководство по выбору для определения приоритета инцидента в Microsoft 365 Defender можно суммировать по формуле: *Severity + Impact = Priority*.

- **Серьезность** — это уровень, назначенный Microsoft 365 Defender и его интегрированные компоненты безопасности.
- **Влияние** определяется организацией и обычно включает, но не ограничивается пороговое число пострадавших пользователей, устройств, служб, затронутых (или их сочетание) и даже типа оповещения.

Затем аналитики инициируют исследования на основе критериев **приоритета,** установленных организацией.

Приоритеты инцидентов могут отличаться в зависимости от организации. NIST рекомендует также учитывать функциональное и информационное влияние инцидента и возможность восстановления.

Ниже приводится только один подход к триаджу:

1. Перейдите на [страницу инцидентов,](incidents-overview.md) чтобы инициировать триадж. Здесь вы можете увидеть список инцидентов, затрагивающих организацию. По умолчанию они расположены от самого последнего до самого старого инцидента. Здесь также можно увидеть различные столбцы для каждого инцидента, показывающие их серьезность, категорию, количество активных оповещений и сущностями с влиянием. Вы можете настроить набор столбцов и сортировать очереди инцидентов по некоторым этим столбцам, выбрав имя столбца. Вы также можете фильтровать очередь инцидента в соответствии с вашими потребностями. Полный список доступных фильтров см. в списке [Prioritize incidents.](incident-queue.md#available-filters)

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-queue.png" alt-text="Пример очереди инцидента":::

    Один из примеров того, как можно выполнить триадж для этого набора инцидентов, — это уделяние приоритетов инцидентам, которые затронули больше пользователей и устройств. В этом примере можно приоритизировать номер инцидента 6769, так как он затрагивает наибольшее число сущностями: 7 устройств, 6 пользователей и 2 почтовых ящика. Кроме того, по всей видимости, в инциденте содержатся оповещения от Microsoft Defender for Identity, которые указывают на предупреждение на основе удостоверений и возможную кражу учетных данных.

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-high-impact.png" alt-text="Пример инцидента с высокими последствиями":::

2. Выберите круг рядом с именем инцидента, чтобы просмотреть сведения. На правой стороне появится боковая часть, которая содержит дополнительные сведения, которые помогут вам в дальнейшем.

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout.png" alt-text="Пример области стороне инцидента":::

   Например, если посмотреть, какую тактику [MITRE ATT&CK,](https://attack.mitre.org/) используемую злоумышленником в зависимости от категорий инцидента, можно приоритизировать этот инцидент, так как злоумышленник использовал украденные учетные данные, установил команду и управление, выполнил поощрительные перемещения и отобрал некоторые данные. Это позволяет предположить, что злоумышленник уже проник в сеть и, возможно, украл конфиденциальную информацию.

   Кроме того, если ваша организация реализовала рамки Zero Trust, доступ к учетным данным будет рассматриваться как важное нарушение безопасности, необходимое для приоритизации.

   Прокручивая боковую часть области, вы увидите определенные объекты, которые влияют на них, такие как пользователи, устройства и почтовые ящики. Вы можете проверить уровень экспозиции каждого устройства и владельцев затронутых почтовых ящиков.

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-details.png" alt-text="Пример сведений о стороне инцидента":::

3. Далее по боковой области можно найти связанные оповещения. Microsoft 365 Defender уже выполнила корреляцию этих оповещений в один инцидент, сэкономив время и ресурсы, которые лучше потратить на исправление атаки. Оповещения являются подозрительными и, следовательно, могут быть вредоносными системные события, которые указывают на наличие злоумышленника в сети.

   В этом примере было установлено, что 87 отдельных оповещений являются частью одного инцидента безопасности. Вы можете просмотреть все оповещения, чтобы получить быстрое представление о том, как была совершена атака.

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-alerts.png" alt-text="Пример оповещений в области стороне инцидента":::

## <a name="analyze-your-first-incident"></a>Анализ первого инцидента

Не менее важно понимать контекст, окружающий оповещения. Часто оповещение — это не одно независимое событие. Существует цепочка созданных процессов, команд и действий, которые могли не иметь место одновременно. Поэтому аналитик должен искать первое и последнее действия подозрительного объекта в временной шкале устройств, чтобы понять контекст оповещений.

Существует несколько способов чтения и анализа данных с помощью Microsoft 365 Defender, но конечная цель аналитиков — как можно быстрее реагировать на инциденты. Хотя Microsoft 365 Defender позволяет значительно сократить время восстановления [(MTTR)](https://www.microsoft.com/security/blog/2020/05/04/lessons-learned-microsoft-soc-part-3c/) с помощью [](m365d-autoir.md) ведущей в отрасли функции автоматического расследования и ответа, всегда есть случаи, которые требуют ручного анализа.

Пример:

1. После того как будет определено приоритетное значение, аналитик начинает углубленный анализ, выбрав имя инцидента. На этой странице приводится **сводка** об инцидентах, в которой данные отображаются на вкладке для оказания помощи в анализе. В **вкладке Alerts** отображается тип оповещений. Аналитики могут щелкнуть каждое оповещение для сверки в соответствующий источник обнаружения.

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-summary-tab.png" alt-text="Пример вкладки Сводка инцидента":::

    Краткое руководство о том, какой домен охватывает каждый источник обнаружения, просмотрите раздел [Detect](#detection-by-microsoft-365-defender) в этой статье.

2. На **вкладке Alerts** аналитик может сделать поворот к источнику обнаружения, чтобы провести более углубленное исследование и анализ. Например, выбор обнаружения вредоносных программ с помощью Microsoft Cloud App Security, так как источник обнаружения принимает аналитика на соответствующую страницу оповещения.

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-select-alert.png" alt-text="Пример выбора оповещений об инциденте":::

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-link-to-mcas.png" alt-text="Пример соответствующей страницы в Microsoft Cloud App Security":::

3. Чтобы изучить наш пример далее, прокрутите в нижней части страницы, чтобы просмотреть **затронутые пользователи.** Чтобы увидеть действия и контекст, связанные с обнаружением вредоносных программ, выберите страницу пользователя Аннет Хилл.

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-user-page.png" alt-text="Пример страницы пользователя":::

4. На странице пользователя находится хронологический список событий, начиная с рискованных входов из оповещений *IP-адресов сети TOR.* В то время как подозрительность действий зависит от характера ведения бизнеса организации, в большинстве случаев использование маршрутизатора лука (TOR), сети, которая позволяет пользователям анонимно просматривать веб-страницы, в корпоративной среде может считаться крайне маловероятным и ненужным для регулярных операций в Интернете.

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-user-event-list.png" alt-text="Пример хронологического списка событий для пользователя":::

5. Для получения дополнительных сведений о действии можно выбрать каждое оповещение. Например, выбор действия из **оповещений IP-адреса Tor** приводит вас к собственной странице оповещения. Аннет является администратором Office 365, что означает, что у нее повышенные привилегии, а инцидент с источником мог привести к доступу к конфиденциальной информации.

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-mcas-alert.png" alt-text="Пример сведений о оповещениях для Microsoft Cloud App Security":::

6. Выбрав другие оповещений, аналитик может получить полную картину атаки.

## <a name="next-step"></a>Следующий этап

[![Шаг 2. Узнайте, как устранять инциденты](../../media/first-incident-overview/first-incident-path-step2.png)](first-incident-remediate.md)

Узнайте, как [устранять инциденты.](first-incident-remediate.md)

## <a name="see-also"></a>См. также

- [Обзор инцидентов](incidents-overview.md)
- [Исследование инцидентов](investigate-incidents.md)
- [Управление инцидентами](manage-incidents.md)
