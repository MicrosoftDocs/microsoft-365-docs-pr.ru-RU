---
title: Обучение экспертов по продвинутой охоте
description: Бесплатное обучение и руководство от специалистов по продвинутым охотам
keywords: продвинутая охота, охота на угрозы, охота на киберугрозы, защита от угроз Майкрософт, Microsoft 365, mtp, m365, поиск, запрос, язык, обучение, сценарии, базовые для расширенных, видео, пошаговой шаг
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 247b8b8d8e18c8eecb09029581635ae907433f55
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076374"
---
# <a name="get-expert-training-on-advanced-hunting"></a>Обучение экспертов по продвинутой охоте

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

Быстро повысить знания о продвинутой охоте с помощью _отслеживания_ противника , серии веб-трансляций для новых аналитиков безопасности и опытных охотников за угрозами. В этой серии вы сможете с помощью основных элементов создать собственные сложные запросы. Начните с первого видео по основам или перейти к более продвинутым видео, которые подходят вашему уровню опыта.


| Должность | Описание | Часы | Запросы | 
|--|--|--|--|
| Эпизод 1. Основы KQL | В этом выпуске освещаются основы продвинутой охоты в Microsoft 365 Defender. Сведения о доступных расширенных данных охоты и основных синтаксисах и операторах KQL. | [YouTube](https://youtu.be/0D9TkGjeJwM?t=351) (54:14) | [CSL-файл](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl) |
| Эпизод 2. Присоединяется | Продолжить изучение данных в области предварительной охоты и совместной работы с таблицами. Узнайте о `inner` , `outer` и `unique` `semi` присоединяется, и понять нюансы по умолчанию kusto `innerunique` присоединиться. | [YouTube](https://youtu.be/LMrO6K5TWOU?t=297) (53:33) | [CSL-файл](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl) |
| Эпизод 3. Обобщение, развязка и визуализация данных | Теперь, когда вы научились фильтровать, управлять данными и присоединяться к ним, пришло время обобщить, оценить, развести и визуализировать. В этом выпуске обсуждаются оператор и различные вычисления, а в схеме вводятся `summarize` дополнительные таблицы. Вы также научитесь превращать наборы данных в диаграммы, которые помогут вам получить представление. | [YouTube](https://youtu.be/UKnk9U1NH6Y?t=296) (48:52) | [CSL-файл](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl) |
| Эпизод 4. Давайте охотиться! Применение KQL для отслеживания инцидентов | В этом эпизоде вы научитесь отслеживать действия злоумышленников. Для отслеживания атаки мы используем улучшенное понимание Kusto и продвинутую охоту. Узнайте о реальных уловках, используемых в поле, в том числе о кибербезопасности и о применении их к реагированию на инциденты. | [YouTube](https://youtu.be/2EUxOc_LNd8?t=291) (59:36) | [CSL-файл](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl) 


Получите дополнительные профессиональные навыки с *помощью L33TSP3AK:* расширенная охота в Microsoft 365 Defender , серия веб-трансляций для аналитиков, которые ищут возможности для расширения своих технических знаний и практических навыков в проведении расследований безопасности с помощью расширенной охоты в Microsoft 365 Defender. 

| Должность | Описание | Часы | Запросы | 
|--|--|--|--|
| Эпизод 1  | В этом выпуске вы узнаете различные методы работы с расширенными запросами на охоту. Среди затронутых тем: оптимизация запросов, использование расширенных запросов для вымогателей, обработка JSON как динамического типа и работа с внешними операторами данных. | [YouTube](https://www.youtube.com/watch?v=nMGbK-ALaVg&feature=youtu.be) (56:34) | [CSL-файл](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/blob/master/Webcasts/l33tSpeak/Performance%2C%20Json%20and%20dynamics%20operator%2C%20external%20data.csl)


## <a name="how-to-use-the-csl-file"></a>Использование CSL-файла
Перед запуском эпизода вы можете получить доступ к соответствующему [CSL-файлу Kusto в GitHub](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/tree/master/Webcasts/TrackingTheAdversary) и скопируйте его содержимое в расширенный редактор запроса на охоту. Во время просмотра эпизода можно использовать скопированные содержимое для просмотра динамика и запуска запросов. 

В следующем отрывке из CSL-файла показан полный набор указаний, помеченных как `//` комментарии.

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

Тот же CSL-файл содержит запросы до и после комментариев, как показано ниже. Чтобы запустить определенный запрос с несколькими [запросами](advanced-hunting-query-language.md#work-with-multiple-queries-in-the-editor)в редакторе, переместим курсор в этот запрос и выберите **выполнить запрос**.   

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
     
## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Познакомьтесь с языком запросов расширенной охоты](advanced-hunting-query-language.md)
- [Работа с результатами запросов](advanced-hunting-query-results.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
