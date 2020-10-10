---
title: Обучение по расширенному поиску в экспертной системе
description: Бесплатные учебные курсы от расширенных экспертов по поиску
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, язык, обучение, сценарии, базовый для расширенных, видео, пошаговые инструкции
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
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: f06cb4190f8932f3a472356ba45adcc3bc35423c
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413322"
---
# <a name="get-expert-training-on-advanced-hunting"></a>Обучение по расширенному поиску в экспертной системе

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Защита от угроз (Майкрософт)

Быстро Повысьте свои знания о расширенном _поиске с_учетом противодействия, серии веб-трансляций для новых аналитиков безопасности и хунтерсных угроз. С помощью этой серии вы узнаете, как создавать собственные сложные запросы. Начните с первого видео на основных понятиях или переходите к дополнительным видеороликам, которые соответствуют вашему уровню работы.


| Название | Описание | Часы | Запросы | 
|--|--|--|--|
| Эпизод 1: базовые понятия KQL | В этой серии рассматриваются основные принципы расширенного Поиск в защите от угроз Майкрософт. Сведения о доступных дополнительных данных по поиску и базовому синтаксису KQL и операторам. | [YouTube](https://youtu.be/0D9TkGjeJwM?t=351) (54:14) | [Файл CSL](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl) |
| Эпизод 2: объединения | Продолжайте изучать данные в расширенном поиске, а также как объединять таблицы. Узнайте о `inner` `outer` `unique` `semi` нюансах соединения Кусто по умолчанию, а также присоединитесь к ним и Узнайте о них `innerunique` . | [YouTube](https://youtu.be/LMrO6K5TWOU?t=297) (53:33) | [Файл CSL](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl) |
| Эпизод 3: сводка, сведение и визуализация данных | Теперь, когда вы узнали, как фильтровать, управлять и присоединять данные, можно подвести итог, количественное представление, сведение и визуализация. В этом эпизоде обсуждается `summarize` оператор и различные вычисления, в результате чего в схему добавляются дополнительные таблицы. Вы также узнаете, как превратить наборы данных в диаграммы, которые помогут вам извлекать информацию. | [YouTube](https://youtu.be/UKnk9U1NH6Y?t=296) (48:52) | [Файл CSL](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl) |
| Эпизод 4: Давайте добавим! Применение KQL к отслеживанию инцидентов | В этом эпизоде вы узнаете, как отслеживать действия злоумышленников. Мы используем наше усовершенствованное понимание Кусто и расширенного поиска для отслеживания атак. Узнайте о фактических приемах, используемых в этом поле, в том числе о Абксе циберсекурити и о том, как применить их к реагированию на инциденты. | [YouTube](https://youtu.be/2EUxOc_LNd8?t=291) (59:36) | [Файл CSL](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl)

## <a name="how-to-use-the-csl-file"></a>Использование файла CSL
Перед запуском эпизода получите доступ к соответствующему [файлу Кусто CSL на сайте GitHub](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/tree/master/Webcasts/TrackingTheAdversary) и скопируйте его содержимое в редактор запросов расширенного поиска. При просмотре эпизода вы можете использовать скопированное содержимое, чтобы следить за динамиком и выполнять запросы. 

Приведенный ниже фрагмент файла CSL содержит полный набор руководств, помеченных как комментарии `//` .

```kusto
// DeviceLogonEvents
// A table containing a row for each logon a device enrolled in Defender ATP
// Contains
// - Account information associated with the logon
// - The device which the account logged onto
// - The process which performed the logon
// - Network information (for network logons)
// - Timestamp
```

Один и тот же файл CSL включает запросы до и после комментариев, как показано ниже. Чтобы запустить определенный запрос с [несколькими запросами в редакторе](advanced-hunting-query-language.md#work-with-multiple-queries-in-the-editor), переместите курсор в этот запрос и выберите команду **выполнить запрос**.   

```kusto
DeviceLogonEvents
| count

// DeviceLogonEvents
// A table containing a row for each logon a device enrolled in Defender ATP
// Contains
// - Account information associated with the logon
// - The device which the account logged onto
// - The process which performed the logon
// - Network information (for network logons)
// - Timestamp

AppFileEvents
| take 100
| sort by Timestamp desc
```
     
## <a name="related-topics"></a>Связанные статьи
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Познакомьтесь с языком запросов расширенной охоты](advanced-hunting-query-language.md)
- [Работа с результатами запросов](advanced-hunting-query-results.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
