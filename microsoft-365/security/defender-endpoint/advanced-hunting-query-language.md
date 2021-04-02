---
title: Познакомьтесь с языком запросов расширенной охоты
description: Создайте ваш первый запрос охоты на угрозы и узнайте о распространенных операторах и других аспектах языка запросов расширенной охоты на угрозы
keywords: передовая охота, охота на угрозы, охота на киберугрозы, mdatp, microsoft defender atp, wdatp search, query, language, learn, first query, telemetry, events, telemetry, custom detections, schema, kusto, operators, data types
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: af612a051f133e4846e04033ab35ea39769d0193
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499546"
---
# <a name="learn-the-advanced-hunting-query-language"></a>Познакомьтесь с языком запросов расширенной охоты

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

Расширенный поиск основывается на [языке запросов Kusto](https://docs.microsoft.com/azure/kusto/query/). Вы можете использовать операторы Kusto и операторы для создания запросов, которые размещают сведения в специализированной [схеме.](advanced-hunting-schema-reference.md) Чтобы лучше понять эти концепции, запустите ваш первый запрос.

## <a name="try-your-first-query"></a>Попробуйте выполнить первый запрос

В Центре безопасности Защитника Майкрософт перейдите в **Службу предварительной охоты** для выполнения первого запроса. Используйте следующий пример:

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
**[Запуск этого запроса в продвинутой охоте](https://securitycenter.windows.com/hunting?query=H4sIAAAAAAAEAI2TT0vDQBDF5yz4HUJPFcTqyZsXqyCIBFvxKNGWtpo_NVlbC8XP7m8mado0K5Zls8nkzdu3b2Z70pNAbmUmqYyk4D2UTJYyllwGMmWNGQHrN_NNvsSBzUBrbMFMiWieAx3xDEBl4GL4AuNd8B0bNgARENcdUmIZ3yM5liPwac3bN-YZPGPU5ET1rWDc7Ox4uod8YDp4MzI-GkjlX4Ne2nly0zEkKzFWh4ZE5sSuTN8Ehq5couvEMnvmUAhez-HsRBMipVa_W_OG6vEfGtT12JRHpqV064e1Kx04NsxFzXxW1aFjp_djXmDRPbfY3XMMcLogTz2bWZ2KqmIJI6q6wKe2WYnrRsa9KVeU9kCBBo2v7BzPxF_Bx2DKiqh63SGoRoc6Njti48z_yL71XHQAcgAur6rXRpcqH3l-4knZF23Utsbq2MircEqmw-G__xR1TdZ1r7zb7XLezmx3etkvGr-ze6NdGdW92azUfpcdluWvr-aqbh_nofnqcWI3aYyOsBV7giduRUO7187LMKTT5rxvHHX80_t8IeeMgLquvL7-Ak3q-kz8BAAA&runQuery=true&timeRangeId=week)**

### <a name="describe-the-query-and-specify-the-tables-to-search"></a>Описание запроса и указание таблиц для поиска
В начале запроса добавлен краткий комментарий, чтобы описать его. Этот комментарий поможет, если позже вы решите сохранить запрос и поделиться им с другими в организации.

```kusto
// Finds PowerShell execution events that could involve a download
```
Сам запрос обычно начинается с имени таблицы с несколькими элементами, которые начинаются с трубки ( `|` ). В этом примере мы начинаем с создания объединения из двух таблиц и добавления элементов по мере  `DeviceProcessEvents` `DeviceNetworkEvents` необходимости.

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a>Установите диапазон времени
Первый элемент с конвейером — это фильтр времени, который был в течение предыдущих семи дней. Ограничение диапазона времени позволяет убедиться, что запросы выполняются хорошо, возвращают управляемые результаты и не отжимаются.

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a>Проверка определенных процессов
За диапазоном времени сразу последует поиск имен файлов процессов, представляющих приложение PowerShell.

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a>Поиск определенных строк команд
После этого запрос ищет строки в строках команд, которые обычно используются для скачивания файлов с помощью PowerShell.

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
Теперь, когда запрос четко определяет данные, которые необходимо найти, можно определить, как выглядят результаты. `project` возвращает определенные столбцы и `top` ограничивает количество результатов. Эти операторы помогают обеспечить, чтобы результаты были хорошо отформатированы и достаточно большие и просты в обработке.

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

Выберите **запрос Run,** чтобы увидеть результаты. Используйте значок расширения в правом верхнем справа от редактора запроса, чтобы сосредоточиться на запросе и результатах поиска. 

![Изображение управления Expand в редакторе расширенного запроса на охоту](images/advanced-hunting-expand.png)

>[!TIP]
>Результаты запроса можно просматривать как диаграммы и быстро настраивать фильтры. Инструкции по [работе с результатами запросов](advanced-hunting-query-results.md)

## <a name="learn-common-query-operators-for-advanced-hunting"></a>Познакомьтесь с обычными операторами запросов для расширенной охоты

Вы только что запустите первый запрос и имеете общее представление о его компонентах. Пришло время немного отойтки и изучить некоторые основы. Язык запросов Kusto, используемый в расширенной охоте, поддерживает ряд операторов, включая обычные, описанные ниже.

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

Чтобы увидеть живой пример этих операторов, запустите их в разделе **Начало** работы на продвинутой странице охоты.

## <a name="understand-data-types"></a>Понимание типов данных

Расширенный поиск поддерживает типы данных Kusto, включая следующие распространенные типы:

| Тип данных | Описание и влияния запроса |
|--|--|
| `datetime` | Данные и сведения о времени, как правило, представляющие время событий. [См. поддерживаемые форматы дат](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | Строка символов в UTF-8, заключенная в одиночные кавычка () или `'` двойные кавычка ( `"` ). [Подробнее о строках](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | Этот тип данных поддерживает `true` или `false` заявляет. [См. поддерживаемые литералы и операторы](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | 32-bit integer  |
| `long` | 64-bit integer |

Дополнительные сведения об этих типах данных читайте в [материале о типах данных Kusto scalar.](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/)

## <a name="get-help-as-you-write-queries"></a>Помощь при написании запросов
Ниже перечислены функции, благодаря которым запросы можно создавать быстрее.

- **Autosuggest**— при записи запросов расширенный поиск предоставляет предложения из IntelliSense.
- **Дерево схемы**— представление схемы, которое включает список таблиц и их столбцов, предоставляется рядом с рабочей областью. Чтобы получить об элементе дополнительные сведения, нужно навести на него указатель мыши. Чтобы вставить элемент в редактор запросов, нужно дважды щелкнуть по нему.
- **[Ссылка схемы](advanced-hunting-schema-reference.md#get-schema-information-in-the-security-center)**— ссылка на портал с описаниями таблиц и столбцов, а также поддерживаемые типы событий `ActionType` (значения) и примеры запросов

## <a name="work-with-multiple-queries-in-the-editor"></a>Работа с несколькими запросами в редакторе
Редактор запроса можно использовать для экспериментов с несколькими запросами. Использование нескольких запросов:

- Отделяйте каждый запрос пустой строкой.
- Поместите курсор в любую часть запроса, чтобы выбрать этот запрос перед его запуском. При этом будет работать только выбранный запрос. Чтобы запустить другой запрос, переместим курсор соответствующим образом и выберите **запрос Run.**

![Изображение редактора расширенных запросов охоты с несколькими запросами ](images/ah-multi-query.png)
 _Редактор запроса с несколькими запросами_

## <a name="use-sample-queries"></a>Использование примеров запросов

Раздел **Начало работы** содержит несколько простых запросов, использующих часто используемые операторы. Попробуйте выполнить эти запросы и внести в них небольшие изменения.

![Изображение вкладки advanced hunting get started](images/atp-advanced-hunting.png)

> [!NOTE]
> Кроме примеров базовых запросов, вы можете получить доступ к [общим запросам](advanced-hunting-shared-queries.md) для определенных сценариев охоты на угрозы. Ознакомьтесь с общими запросами на левой стороне страницы или репозиторием [запросов GitHub.](https://aka.ms/hunting-queries)

## <a name="access-comprehensive-query-language-reference"></a>Доступ к комплексной языковой ссылке запроса

Подробные сведения о языке запросов см. в документации [по языку запросов Kusto.](https://docs.microsoft.com/azure/kusto/query/)

## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенной охоты](advanced-hunting-overview.md)
- [Работа с результатами запросов](advanced-hunting-query-results.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Сведения о схеме](advanced-hunting-schema-reference.md)
- [Применение рекомендаций по использованию запросов](advanced-hunting-best-practices.md)
