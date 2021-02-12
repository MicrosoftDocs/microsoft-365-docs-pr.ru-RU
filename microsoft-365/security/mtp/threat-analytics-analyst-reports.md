---
title: Обзор раздела отчета аналитики в аналитике угроз
ms.reviewer: ''
description: Узнайте о разделе отчета аналитики для каждого отчета аналитики угроз. Сведения об угрозах, средствах утежения, обнаружении, расширенных запросах вынаружения и многого другго.
keywords: аналитический отчет, аналитика угроз, обнаружение, расширенные запросы вынаружения, меры,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 650282e0dce49cc392eeb7501f91b3ffed9f0707
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167569"
---
# <a name="understand-the-analyst-report-in-threat-analytics"></a>Анализ отчета аналитики в аналитике угроз

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**
- Microsoft 365 Defender

> Хотите испытать Microsoft 365 Defender? Вы можете [оценить его в лабораторной среде](https://aka.ms/mtp-trial-lab) или запустить [пилотный проект в производственной среде.](https://aka.ms/m365d-pilotplaybook)
>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Каждый [отчет аналитики угроз](threat-analytics.md) включает в себя динамические разделы и полный письменный раздел, называемый _отчетом аналитика._ Чтобы открыть этот раздел, откройте отчет о отслеживаемой угрозе и выберите вкладку **"Отчет** аналитика".

![Изображение раздела отчета аналитики отчета аналитики угроз](../../media/threat-analytics/ta_analystreport_mtp.png)

_Раздел отчета аналитики отчета аналитики угроз_

## <a name="scan-the-analyst-report"></a>Сканирование отчета аналитика 
Каждый раздел отчета аналитика предназначен для предоставления информации с действиями. Хотя отчеты различаются, большинство отчетов включают разделы, описанные в следующей таблице.

| Раздел "Отчет" | Описание |
|--|--|
| Сводка по исполнительным руководствам | Обзор угрозы, включая ее первое представление, ее мотивы, важные события, основные цели, а также отдельные инструменты и методы. Эти сведения можно использовать для дальнейшей оценки приоритетов угрозы в контексте отрасли, географического расположения и сети. |
| Анализ | Техническая информация об угрозах, включая сведения об атаке и о том, как злоумышленники могут использовать новую методику или поверхность атаки | 
| Методы MITRE ATT&CK | Как наблюдаемые методы соотнося с [структурой атак MITRE ATT&CK](https://attack.mitre.org/) | 
| [Меры по смягчению последствий](#apply-additional-mitigations) | Рекомендации, которые могут остановить или уменьшить влияние угрозы. В этом разделе также содержатся меры, которые динамически не отслеживаются в отчете аналитики угроз. |
| [Сведения об обнаружении](#understand-how-each-threat-can-be-detected) | Конкретные и универсальные обнаружения, предоставляемые решениями майкрософт по обеспечению безопасности, которые могут выявлять действия или компоненты, связанные с угрозой. | 
| [Расширенная охота на угрозы](#find-subtle-threat-artifacts-using-advanced-hunting) | [Расширенные поисковые запросы](advanced-hunting-overview.md) для заблаговременной идентификации возможных действий с угрозами. Большинство запросов предоставляется в дополнение к обнаружению, особенно для обнаружения потенциально вредоносных компонентов или поведения, которые не могут быть динамически оценены как вредоносные. | 
| Ссылки | Публикации Майкрософт и сторонних продуктов, на которые ссылались аналитики при создании отчета. Контент аналитики угроз основан на данных, проверенных исследователями Майкрософт. Информация из общедоступных сторонних источников четко определена как таковая. | 
| Журнал изменений | Время публикации отчета и внесение значительных изменений в отчет. |

## <a name="apply-additional-mitigations"></a>Применение дополнительных утех
Аналитика угроз динамически отслеживает состояние обновлений [безопасности и безопасных конфигураций.](threat-analytics.md#mitigations-review-list-of-mitigations-and-the-status-of-your-devices) Эти сведения доступны в качестве диаграмм и таблиц на вкладке **"Меры".**

В дополнение к этим отслеживаемой меры, в отчете аналитика  также обсуждаются меры, которые не отслеживаются динамически. Вот несколько примеров важных утех, которые динамически не отслеживаются.

- Блокировка сообщений электронной _почты с LNK-вложениями_ или другими подозрительными типами файлов
- Случайный выбор паролей локального администратора
- Информирование конечных пользователей о фишинге электронной почты и других векторах угроз
- Включить определенные правила [уменьшения поверхности атаки](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)

Несмотря на то что вкладку **"Меры"** можно использовать для оценки вашего положения в области безопасности от угрозы, эти рекомендации могут помочь вам предпринять дополнительные действия по улучшению безопасности. Внимательно ознакомьтесь со всеми рекомендациями по смягчению последствий в отчете аналитика и по возможности применяйте их.

## <a name="understand-how-each-threat-can-be-detected"></a>Понять, как можно обнаружить каждую угрозу
Отчет аналитика также содержит определения антивирусной программы endpoint и функций обнаружения конечных точек и _реагирования_ на них в Microsoft Defender.

### <a name="antivirus-detections"></a>Обнаружение вирусов
Эти обнаружения доступны на устройствах с включенной антивирусной программой [Microsoft Defender.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) Когда эти обнаружения происходят на устройствах, которые были перенабором в Microsoft Defender для конечной точки, они также вызывают оповещения, которые активирует диаграммы в отчете.

>[!NOTE]
>В отчете  аналитика также перечислены универсальные обнаружения, которые могут определять широкий диапазон угроз, в дополнение к компонентам или поведениям, характерным для отслеживаемой угрозы. Эти универсальные обнаружения не отражаются на диаграммах.

### <a name="endpoint-detection-and-response-edr-alerts"></a>Оповещения об обнаружении конечных точек и ответе (EDR)
Оповещения EDR вызываются для устройств, которые были переназначны [в Microsoft Defender для конечной точки.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure) Эти оповещения обычно зависят от сигналов безопасности, собранных Microsoft Defender для датчиков конечных точек, и других возможностей конечных точек, таких как антивирусная программа, защита сети, защита от взлома, которые служат в качестве мощных источников сигналов.

Как и список обнаружений антивирусных программ, некоторые оповещения EDR предназначены для универсального пометки подозрительного поведения, которое не может быть связано с отслеживаемой угрозой. В таких случаях отчет четко определяет оповещение как "универсальное" и не влияет ни на какие диаграммы в отчете.

### <a name="email-related-detections-and-mitigations"></a>Обнаружение и меры, связанные с электронной почтой
Обнаружения и меры, связанные с электронной почтой, из Microsoft Defender для Office 365 включаются в отчеты аналитиков в дополнение к данным конечной точки, уже доступным в Microsoft Defender для конечной точки. 

Сведения о предотвращенных попытках электронной почты дают вам представление о том, была ли ваша организация целью угрозы, которая была предпринята в отчете аналитика, даже если атака была фактически заблокирована до доставки или доставки в папку нежелательной почты.

## <a name="find-subtle-threat-artifacts-using-advanced-hunting"></a>Поиск незначительных артефактов угроз с помощью расширенных методов поиска
Хотя обнаружение позволяет автоматически определять и останавливать отслеживаемую угрозу, многие действия по атакам оставляют незначительные трассировки, которые требуют дополнительной проверки. Некоторые действия по атакам также могут быть обычными, поэтому динамическое их обнаружение может привести к рабочему шуму или даже ложным срабатываниям.

[Расширенный поиск](advanced-hunting-overview.md) предоставляет интерфейс запроса на основе языка запросов Kusto, который упрощает поиск незначительных индикаторов активности угроз. Это также позволяет получить контекстную информацию и проверить, подключены ли индикаторы к угрозе.

Запросы на расширенный поиск в отчетах аналитиков были запрос кортегов аналитиками Майкрософт и готовы к запуску в редакторе запросов на расширенный [поиск.](https://security.microsoft.com/advanced-hunting) Вы также можете использовать запросы для создания пользовательских правил [обнаружения,](custom-detection-rules.md) которые запускают оповещения для будущих совпадений.


>[!NOTE]
> Аналитика угроз также доступна в [Microsoft Defender для конечной точки.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) Однако в нем нет интеграции данных между Microsoft Defender для Office и Microsoft Defender для конечной точки, которая есть в аналитике угроз в Microsoft 365 Defender.


## <a name="related-topics"></a>Связанные статьи
- [Обзор аналитики угроз](threat-analytics.md)
- [Заблаговременное поиск угроз с расширенным поиском](advanced-hunting-overview.md) 
- [Настраиваемые правила обнаружения](custom-detection-rules.md)