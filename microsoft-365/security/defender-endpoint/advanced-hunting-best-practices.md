---
title: Запрос лучших методов для продвинутой охоты
description: В этой статье можно узнать о том, как формировать оперативные, эффективные и безошибочные запросы в ходе расширенного выслеживания.
keywords: передовая охота, охота на угрозы, охота на киберугрозы, mdatp, защита microsoft atp, поиск wdatp, запрос, телеметрия, настраиваемые обнаружения, схема, кусто, избегайте времени, командных строк, id процесса
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
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b65adbc968e095a6845f27ae1ae859830e4065c4
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499256"
---
# <a name="advanced-hunting-query-best-practices"></a>Рекомендации по использованию запросов расширенного выслеживания

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-bestpractices-abovefoldlink)

## <a name="optimize-query-performance"></a>Оптимизация производительности запросов

Применяем эти рекомендации, чтобы быстрее получать результаты и избегать периодов времени во время работы сложных запросов.

- Чтобы избежать чрезвычайно больших наборов результатов, при попытках ввода новых запросов нужно всегда использовать `limit`. Кроме того, с помощью `count` можно заранее задать размеры набора результатов.
- Временные фильтры рекомендуется применять в первую очередь. В идеале ограничьте запросы семи днями.
- Рекомендуется устанавливать фильтры, предназначенные для удаления большей части данных в начале запроса, сразу после применения временного фильтра.
- При поиске полных маркеров нужно использовать оператор `has` вместо `contains`.
- Вместо полнотекстового поиска во всех столбцах рекомендуется осуществлять поиск в определенном столбце.
- При объединении таблиц сначала нужно указать таблицу с меньшим количеством строк.
- Использовать оператор`project` следует только для необходимых столбцов объединенных таблиц.

>[!TIP]
>Дополнительные руководства по повышению производительности запросов см. в статье [Рекомендации по использованию запросов Kusto](https://docs.microsoft.com/azure/kusto/query/best-practices).

## <a name="query-tips-and-pitfalls"></a>Подсказки и ловушки, связанные с запросами

### <a name="queries-with-process-ids"></a>Запросы с идентификаторами процессов

Идентификаторы процессов (PID) в Windows перерабатываются и используются для новых процессов. Они не могут служить уникальными идентификаторами для определенных процессов сами по себе. Чтобы получить уникальный идентификатор для процесса на определенном устройстве, используйте идентификатор процесса вместе с временем создания процесса. Когда вы присоединяется или суммируете данные вокруг процессов, включаем столбцы для идентификатора устройства (либо или), идентификатора процесса (или) и времени создания процесса `DeviceId` `DeviceName` `ProcessId` `InitiatingProcessId` `ProcessCreationTime` `InitiatingProcessCreationTime` (или).

В приведенном ниже примере запроса обнаружены процессы, имеющие доступ к более чем 10 IP-адресам через порт 445 (SMB) с одновременным возможным сканированием файловых ресурсов.

```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId, InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

В запросе указаны одновременно и `InitiatingProcessId`, и `InitiatingProcessCreationTime`. Благодаря этому запрос относится к одному единственному процессу, и при этом исключаются многочисленные другие процессы с аналогичным идентификатором процесса.

### <a name="queries-with-command-lines"></a>Запросы с командными строками

Существует множество разнообразных командных строк. При необходимости можно выполнить фильтрацию по названиям файлов и осуществить поиск нечетких соответствий.

Создать командную строку для выполнения задачи можно разными способами. Например, злоумышленник может создать ссылку на файл с изображением с путем или без него, без расширения файла, используя переменные среды, или с кавычками. Кроме того, злоумышленник может изменить порядок параметров или добавить несколько кавычек и пробелов.

Ниже приводятся рекомендации для создания более устойчивых запросов с помощью командных строк.

- Указывать известные процессы (такие как *net.exe* или *psexec.exe*) нужно, используя соответствия полей имен файлов вместо применения фильтра для поля командной строки.
- При запросе аргументов командной строки искать точное совпадение для нескольких несвязанных аргументов в определенном порядке не имеет смысла. Вместо этого используются регулярные выражения или несколько отдельных аргументов, содержащих операторы.
- Совпадения используются без учета регистра. Например, используйте `=~` `in~` , и вместо , `contains` `==` `in` и `contains_cs`
- Чтобы предотвратить случаи сокрытия назначения командной строки в DOS, можно удалить кавычки, заменив их пробелами и заменив несколько пробелов одним. Нужно помнить о том, что существуют более сложные методы маскирования в DOS, для борьбы с которыми требуются другие подходы, но вышеуказанные способы обычно помогают в наиболее распространенных случаях.

В приведенных ниже примерах предлагаются различные способы создания запроса для поиска файла *net.exe* для остановки службы брандмауэра Защитника Windows.

```kusto
// Non-durable query - do not use
DeviceProcessEvents
| where ProcessCommandLine == "net stop MpsSvc"
| limit 10

// Better query - filters on filename, does case-insensitive matches
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe") and ProcessCommandLine contains "stop" and ProcessCommandLine contains "MpsSvc" 

// Best query also ignores quotes
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe")
| extend CanonicalCommandLine=replace("\"", "", ProcessCommandLine)
| where CanonicalCommandLine contains "stop" and CanonicalCommandLine contains "MpsSvc" 
```

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-bestpractices-belowfoldlink)

## <a name="related-topics"></a>Статьи по теме

- [Обзор расширенной охоты](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Сведения о схеме](advanced-hunting-schema-reference.md)
- [Работа с результатами запросов](advanced-hunting-query-results.md)
- [Обзор настраиваемых обнаружений](overview-custom-detections.md)
