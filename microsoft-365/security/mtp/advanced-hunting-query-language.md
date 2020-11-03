---
title: Сведения о расширенном поиске на языке запросов в защитнике Microsoft 365
description: Создайте ваш первый запрос охоты на угрозы и узнайте о распространенных операторах и других аспектах языка запросов расширенной охоты на угрозы
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, язык, сведения, первый запрос, телеметрии, события, телеметрии, пользовательские обнаружения, схема, события, телеметрии, пользовательские обнаружения, схема, Кусто, операторы, типы данных, Загрузка PowerShell, пример запроса
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
ms.openlocfilehash: bb3caff642e752cb6d3941b697820fbad69ae23c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841980"
---
# <a name="learn-the-advanced-hunting-query-language"></a>Познакомьтесь с языком запросов расширенной охоты

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Защитник Microsoft 365

Расширенный поиск основывается на [языке запросов Kusto](https://docs.microsoft.com/azure/kusto/query/). Вы можете использовать операторы и операторы Кусто для создания запросов, которые находят информацию в специализированной [схеме](advanced-hunting-schema-tables.md). Чтобы лучше понять эти концепции, запустите ваш первый запрос.

## <a name="try-your-first-query"></a>Попробуйте выполнить первый запрос

В центре безопасности Microsoft 365 выберите Поиск, **чтобы запустить** первый запрос. Используйте следующий пример:

```kusto
// Finds PowerShell execution events that could involve a download
union DeviceProcessEvents, DeviceNetworkEvents
| where Timestamp > ago(7d)
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
// Suspicious commands
| where ProcessCommandLine has_any("WebClient",
 "DownloadFile",
 "DownloadData",
 "DownloadString",
"WebRequest",
"Shellcode",
"http",
"https")
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

**[Запустить этот запрос в расширенном поиске](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**

### <a name="describe-the-query-and-specify-the-tables-to-search"></a>Опишите запрос и укажите таблицы для поиска
В начале запроса добавлен краткий комментарий, описывающий его назначение. Этот комментарий помогает, если позже вы решите сохранить запрос и поделиться им с другими пользователями в Организации. 

```kusto
// Finds PowerShell execution events that could involve a download
```

Как правило, сам запрос начинается с имени таблицы, за которым следуют несколько элементов, которые начинаются с канала ( `|` ). В этом примере мы начнем с создания объединения двух таблиц  `DeviceProcessEvents` и добавления элементов перегрузки `DeviceNetworkEvents` по мере необходимости.

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a>Задание диапазона времени
Первый элемент, который является фильтром по времени, ограничивается на предыдущие семь дней. Ограничение диапазона времени гарантирует, что запросы работают хорошо, возвращают управляемые результаты и не истекает время ожидания.

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a>Проверка определенных процессов
За диапазоном времени следует Поиск имен файлов процессов, представляющих приложение PowerShell.

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a>Поиск определенных командных строк
Затем запрос выполняет поиск строк в командных строках, которые обычно используются для загрузки файлов с помощью PowerShell.

```kusto
// Suspicious commands
| where ProcessCommandLine has_any("WebClient",
    "DownloadFile",
    "DownloadData",
    "DownloadString",
    "WebRequest",
    "Shellcode",
    "http",
    "https")
```

### <a name="customize-result-columns-and-length"></a>Настройка столбцов результатов и длины 
Теперь, когда запрос ясно определяет данные, которые вы хотите найти, вы можете определить, как выглядят результаты. `project` Возвращает определенные столбцы и позволяет `top` ограничить количество результатов. Эти операторы помогают убедиться в том, что результаты имеют правильный формат и их достаточно велики и просты в обработке.

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

Выберите команду **выполнить запрос** , чтобы просмотреть результаты. Используйте значок развертывания в правом верхнем углу редактора запросов, чтобы сосредоточиться на запросе поиска и результатах поиска. 

![Изображение элемента управления "развернуть" в редакторе запросов поиска с расширенным поиском](../../media/advanced-hunting-expand.png)

>[!TIP]
>Вы можете просматривать результаты запроса в виде диаграмм и быстро настраивать фильтры. Рекомендации по [работе с результатами запросов](advanced-hunting-query-results.md)

## <a name="learn-common-query-operators"></a>Общие сведения об операторах запросов

Вы только что выпустили первый запрос и обладаете общей идеей его компонентов. Вы научитесь немного вернуться и изучите основы. Язык запросов Kusto, используемый в расширенной охоте, поддерживает ряд операторов, включая обычные, описанные ниже.

| Оператор | Описание и использование |
|--|--|
| `where` | Фильтрация таблицы по подмножеству строк, удовлетворяющих предикату. |
| `summarize` | Создание таблицы, в которой объединяется содержимое исходной таблицы. |
| `join` | Объединение строк двух таблиц, чтобы сформировать новую таблицу, сопоставляя значения заданных столбцов из каждой таблицы. |
| `count` | Возврат количества записей в исходный набор записей. |
| `top` | Возврат первых N записей, отсортированных по заданным столбцам. |
| `limit` | Возврат до заданного количества строк. |
| `project` | Выбор столбцов, которые нужно включить, переименовать или перетащить, и вставка новых вычисляемых столбцов. |
| `extend` | Создание вычисляемых столбцов и их добавление в результирующий набор. |
| `makeset` |  Возврат динамического массива (JSON) множества различных значений, которые выражение (Expr) принимает в группе. |
| `find` | Поиск строк, соответствующих предикату, по набору таблиц. |

Чтобы просмотреть реальные примеры этих операторов, запустите их из пункта **Начать работу** в разделе Расширенная охота.

## <a name="understand-data-types"></a>Общие сведения о типах данных

Расширенный поиск поддерживает типы данных Кусто, в том числе следующие общие типы:

| Тип данных | Описание и влияния запроса |
|--|--|
| `datetime` | Данные и сведения о времени обычно представляют временные метки событий. [Просмотр поддерживаемых форматов даты и времени](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | Строка символов в кодировке UTF-8, заключенная в одинарные кавычки ( `'` ) или двойные кавычки ( `"` ). [Дополнительные сведения о строках](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | Этот тип данных поддерживает `true` или имеет `false` состояние. [Просмотр поддерживаемых литералов и операторов](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | 32 — разрядное целое число  |
| `long` | 64 — разрядное целое число |

Чтобы узнать больше об этих типах данных, [прочитайте о скалярных типах данных Кусто](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/).

## <a name="get-help-as-you-write-queries"></a>Помощь при написании запросов
Ниже перечислены функции, благодаря которым запросы можно создавать быстрее.
- Автозаполнение **— при** написании запросов Расширенный поиск предоставляет рекомендации от IntelliSense. 
- **Дерево схемы** — представление схемы, включающее список таблиц и их столбцов, предоставляется рядом с рабочей областью. Чтобы получить об элементе дополнительные сведения, нужно навести на него указатель мыши. Чтобы вставить элемент в редактор запросов, нужно дважды щелкнуть по нему.
- **[Справочник по схеме](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** — ссылка на портал со описаниями таблиц и столбцов, а также поддерживаемые типы событий ( `ActionType` значения) и примеры запросов

## <a name="work-with-multiple-queries-in-the-editor"></a>Работать с несколькими запросами в редакторе
С помощью редактора запросов можно поэкспериментировать с несколькими запросами. Чтобы использовать несколько запросов, выполните указанные ниже действия.

- Разделяйте каждый запрос на пустую строку.
- Поместите курсор в любую часть запроса, чтобы выбрать этот запрос перед его запуском. При этом будет запущен только выбранный запрос. Чтобы выполнить другой запрос, переместите курсор соответствующим образом и выберите команду **выполнить запрос**.

![Изображение редактора запросов с несколькими запросами](../../media/mtp-ah/ah-multi-query.png)

## <a name="use-sample-queries"></a>Использование примеров запросов

Раздел **Начало работы** содержит несколько простых запросов, использующих часто используемые операторы. Попробуйте выполнить эти запросы и внести в них небольшие изменения.

![Изображение окна расширенной охоты](../../media/advanced-hunting-get-started.png)

>[!NOTE]
>Кроме примеров базовых запросов, вы можете получить доступ к [общим запросам](advanced-hunting-shared-queries.md) для определенных сценариев охоты на угрозы. Изучите общие запросы, расположенные в левой части страницы, или в [репозитории GitHub запросов GitHub](https://aka.ms/hunting-queries).

## <a name="access-query-language-documentation"></a>Документация по языку условий запросов

Дополнительные сведения о языке запросов Kusto и поддерживаемых операторах см. в статье [Документация по языку запросов Kusto](https://docs.microsoft.com/azure/kusto/query/).

## <a name="related-topics"></a>См. также
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Работа с результатами запросов](advanced-hunting-query-results.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
