---
title: Узнайте, как узнать язык запросов на расширенный поиск в Microsoft 365 Defender
description: Создайте ваш первый запрос охоты на угрозы и узнайте о распространенных операторах и других аспектах языка запросов расширенной охоты на угрозы
keywords: расширенный поиск, охота на угрозы, поиск киберугроз, защита от угроз (Майкрософт), Microsoft 365, mtp, m365, поиск, запрос, язык, сведения, первый запрос, телеметрия, события, телеметрия, пользовательские обнаружения, схема, kusto, операторы, типы данных, загрузка powershell, пример запроса
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
ms.openlocfilehash: 41341a2b5238485fc58021fe4af71cd5c635352c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929806"
---
# <a name="learn-the-advanced-hunting-query-language"></a>Познакомьтесь с языком запросов расширенной охоты

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

Расширенный поиск основывается на [языке запросов Kusto](https://docs.microsoft.com/azure/kusto/query/). Операторы и операторы Kusto можно использовать для создания запросов, которые могут находить информацию в специальной [схеме.](advanced-hunting-schema-tables.md) Чтобы лучше понять эти концепции, запустите ваш первый запрос.

## <a name="try-your-first-query"></a>Попробуйте выполнить первый запрос

В Центре безопасности Microsoft 365 перейдите в службу **"Охота",** чтобы выполнить свой первый запрос. Используйте следующий пример:

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

**[Запустите этот запрос в advanced hunting](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**

### <a name="describe-the-query-and-specify-the-tables-to-search"></a>Описание запроса и указание таблиц для поиска
В начало запроса добавлен короткий комментарий, описывающий его. Этот комментарий поможет вам позже сохранить запрос и поделиться им с другими людьми в вашей организации. 

```kusto
// Finds PowerShell execution events that could involve a download
```

Запрос обычно начинается с имени таблицы, за которым следует несколько элементов, которые начинаются с конвейера ( `|` ). В этом примере мы начнем с создания объединения из двух таблиц и добавляем по конвейеру  `DeviceProcessEvents` `DeviceNetworkEvents` элементы по мере необходимости.

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a>Настройка диапазона времени
Первый элемент, по конвейеру, — это фильтр времени, областью действия в течение предыдущих семи дней. Ограничение диапазона времени позволяет гарантировать, что запросы будут работать хорошо, возвращать управляемые результаты и не дополним время их выполнения.

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a>Проверка определенных процессов
За диапазоном времени сразу же следует поиск имен файлов процессов, представляющих приложение PowerShell.

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a>Поиск определенных строк команд
После этого запрос ищет строки в командных строках, которые обычно используются для скачивания файлов с помощью PowerShell.

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

### <a name="customize-result-columns-and-length"></a>Настройка столбцов и длины результатов 
Теперь, когда запрос четко определяет данные, которые вы хотите найти, вы можете определить, как будут выглядеть результаты. `project` возвращает определенные столбцы и `top` ограничивает число результатов. Эти операторы помогают гарантировать, что результаты будут хорошо отформатированы, достаточно большими и простыми в обработке.

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

Выберите **запрос "Выполнить",** чтобы увидеть результаты. Используйте значок расширения в верхней правой части редактора запросов, чтобы сосредоточиться на запросе поиска и результатах. 

![Изображение управления "Развернуть" в редакторе запросов расширенной охоты](../../media/advanced-hunting-expand.png)

>[!TIP]
>Вы можете просматривать результаты запроса как диаграммы и быстро настраивать фильтры. Инструкции по [работе с результатами запроса](advanced-hunting-query-results.md)

## <a name="learn-common-query-operators"></a>Общие операторы запросов

Вы только что запустите свой первый запрос и имеете общее представление о его компонентах. Пора немного откатить назад и изучить некоторые основы. Язык запросов Kusto, используемый в расширенной охоте, поддерживает ряд операторов, включая обычные, описанные ниже.

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

## <a name="understand-data-types"></a>Сведения о типах данных

Расширенный поиск поддерживает типы данных Kusto, включая следующие распространенные типы:

| Тип данных | Описание и влияния запроса |
|--|--|
| `datetime` | Данные и сведения о времени, как правило, представляющие метки времени события. [См. поддерживаемые форматы даты и времени](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | Строка символов в UTF-8, заключенная в одиночные кавычка ( ) или `'` двойные кавычка ( `"` ). [Дополнительные информацию о строках](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | Этот тип данных поддерживает или `true` `false` состояния. [См. поддерживаемые литералы и операторы](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | 32-битное integer  |
| `long` | 64-битное integer |

Дополнительные сведения об этих типах данных можно узнать [о скалярных типах данных Kusto.](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/)

## <a name="get-help-as-you-write-queries"></a>Помощь при написании запросов
Ниже перечислены функции, благодаря которым запросы можно создавать быстрее.
- **Autosuggest**— при написании запросов расширенный поиск предоставляет предложения от IntelliSense. 
- **Дерево схемы**— представление схемы, которое включает список таблиц и их столбцов, предоставляется рядом с рабочей областью. Чтобы получить об элементе дополнительные сведения, нужно навести на него указатель мыши. Чтобы вставить элемент в редактор запросов, нужно дважды щелкнуть по нему.
- **[Справочник по схеме](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**— справка на портале с описаниями таблиц и столбцов, а также поддерживаемые типы событий ( значения) и `ActionType` примеры запросов

## <a name="work-with-multiple-queries-in-the-editor"></a>Работа с несколькими запросами в редакторе
Редактор запросов можно использовать для экспериментов с несколькими запросами. Чтобы использовать несколько запросов:

- Отделяйте каждый запрос пустой строкой.
- Поместите курсор в любую часть запроса, чтобы выбрать этот запрос перед его запуском. При этом будет запускаться только выбранный запрос. Чтобы запустить другой запрос, переместийте курсор соответствующим образом и выберите запрос **"Выполнить".**

![Изображение редактора запросов с несколькими запросами](../../media/mtp-ah/ah-multi-query.png)

## <a name="use-sample-queries"></a>Использование примеров запросов

Раздел **Начало работы** содержит несколько простых запросов, использующих часто используемые операторы. Попробуйте выполнить эти запросы и внести в них небольшие изменения.

![Изображение окна расширенной охоты](../../media/advanced-hunting-get-started.png)

>[!NOTE]
>Кроме примеров базовых запросов, вы можете получить доступ к [общим запросам](advanced-hunting-shared-queries.md) для определенных сценариев охоты на угрозы. Изучите общие запросы в левой части страницы или репозитория запросов [GitHub.](https://aka.ms/hunting-queries)

## <a name="access-query-language-documentation"></a>Документация по языку условий запросов

Дополнительные сведения о языке запросов Kusto и поддерживаемых операторах см. в статье [Документация по языку запросов Kusto](https://docs.microsoft.com/azure/kusto/query/).

## <a name="related-topics"></a>См. также
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Работа с результатами запросов](advanced-hunting-query-results.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
