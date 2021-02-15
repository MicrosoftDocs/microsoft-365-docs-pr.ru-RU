---
title: Получите экспертное обучение по расширенным охотам
description: Бесплатное обучение и руководство от экспертов по расширенным охотам
keywords: расширенный поиск, охота на угрозы, охота на киберугрозы, защита от угроз (Майкрософт), Microsoft 365, mtp, m365, поиск, запрос, язык, обучение, сценарии, базовые для расширенных, видео, пошаг
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: aba0a6ab2c82c038eda8e66890c0c95303dea947
ms.sourcegitcommit: ea8a096df5acedecdce1780969f2b189c3fadf73
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2021
ms.locfileid: "50053839"
---
# <a name="get-expert-training-on-advanced-hunting"></a>Получите экспертное обучение по расширенным охотам

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

Быстро повысьте знания о расширенных охотах с помощью _"Отслеживание_ злоумышленника", серии веб-трансляций для новых аналитиков безопасности и опытных угроз. В ряду статей вы сможете с основами создать собственные сложные запросы. Начните с первого видео об основах или переначните с более сложных видео, которые подходят для вашего уровня работы.


| Название | Description | Часы | Запросы | 
|--|--|--|--|
| Серия 1. Основы KQL | В этом выпуске освещаются основы расширенных охот в Microsoft 365 Defender. Сведения о доступных расширенных данных охоты и базовом синтаксис и операторах KQL. | [YouTube](https://youtu.be/0D9TkGjeJwM?t=351) (54:14) | [CSL-файл](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl) |
| Серия 2. Joins | Продолжайте изучение данных в расширенных охотах и о том, как объединить таблицы. Узнайте о , , и присоединяется, и понять нюансы `inner` `outer` `unique` `semi` присоединить Kusto по `innerunique` умолчанию. | [YouTube](https://youtu.be/LMrO6K5TWOU?t=297) (53:33) | [CSL-файл](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl) |
| Видео 3. Суммирование, списание и визуализация данных | Теперь, когда вы научились фильтровать, управлять данными и присоединять их, пришло время суммировать, оценить, свести итоги и визуализировать их. В этом выпуске обсуждается оператор и различные вычисления, в то же время в схеме внедряются `summarize` дополнительные таблицы. Вы также узнаете, как превратить наборы данных в диаграммы, которые помогут вам получить представление. | [YouTube](https://youtu.be/UKnk9U1NH6Y?t=296) (48:52) | [CSL-файл](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl) |
| Серия 4. Давайте поохотимся! Применение KQL к отслеживанию инцидентов | В этом случае вы научитесь отслеживать некоторые действия злоумышленников. Мы используем улучшенное понимание Kusto и расширенный поиск для отслеживания атаки. Узнайте о фактических приемах, используемых в этой области, в том числе о правилах кибербезопасности и о том, как применять их к реагированию на инциденты. | [YouTube](https://youtu.be/2EUxOc_LNd8?t=291) (59:36) | [CSL-файл](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl) 


Получите более экспертное обучение с *помощью L33TSP3AK:* расширенный поиск в Microsoft 365 Defender , серия веб-трансляций для аналитиков, которые ищут, чтобы расширить свои технические знания и практические навыки в проведении расследований безопасности с помощью расширенного выслеживания в Microsoft 365 Defender. 

| Название | Description | Часы | Запросы | 
|--|--|--|--|
| Серия 1  | В этом выпуске вы узнаете о различных методиках работы с расширенными поисковыми запросами. В число тем входит: как оптимизировать запросы, использовать расширенный поиск программ-вымогателей, обрабатывать JSON как динамический тип и работать с внешними операторами данных. | [YouTube](https://www.youtube.com/watch?v=nMGbK-ALaVg&feature=youtu.be) (56:34) | [CSL-файл](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/blob/master/Webcasts/l33tSpeak/Performance%2C%20Json%20and%20dynamics%20operator%2C%20external%20data.csl)


## <a name="how-to-use-the-csl-file"></a>Использование CSL-файла
Прежде чем начинать видео, перезапуските соответствующий [CSL-файл Kusto на GitHub](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/tree/master/Webcasts/TrackingTheAdversary) и скопируйте его содержимое в редактор запросов на расширенный поиск. При просмотре видео можно использовать скопированные материалы для просмотра динамика и запуска запросов. 

В следующем фрагменте CSL-файла показан полный набор рекомендаций, помеченных как `//` комментарии.

```kusto
// DeviceLogonEvents
// A table containing a row for each logon a device enrolled in Microsoft Defender for Endpoint
// Contains
// - Account information associated with the logon
// - The device which the account logged onto
// - The process which performed the logon
// - Network information (for network logons)
// - Timestamp
```

Тот же CSL-файл содержит запросы до и после комментариев, как показано ниже. Чтобы выполнить определенный запрос с несколькими [запросами](advanced-hunting-query-language.md#work-with-multiple-queries-in-the-editor)в редакторе, переместим курсор в этот запрос и выберите запрос **"Выполнить".**   

```kusto
DeviceLogonEvents
| count

// DeviceLogonEvents
// A table containing a row for each logon a device enrolled in Microsoft Defender for Endpoint
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
