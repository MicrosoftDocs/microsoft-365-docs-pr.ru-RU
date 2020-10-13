---
title: Обработка ошибок в расширенном поиске для защиты от угроз Майкрософт
description: Общие сведения об ошибках, отображаемых при расширенном поиске
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, схема, Кусто, время ожидания, ресурсы, ошибки, неизвестная ошибка
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
ms.openlocfilehash: 27eb3558e00e1fc8f747ee7e88dbb986256ea8ed
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429627"
---
# <a name="handle-advanced-hunting-errors"></a>Обработка дополнительных ошибок при поиске

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


При расширенном поиске отображаются ошибки, уведомляющие о синтаксических ошибках и о [предопределенных пределах](advanced-hunting-limits.md)запросов. В таблице ниже приведены советы по устранению ошибок и их устранению. 

| Тип "ошибка" | Причина | Решение | Примеры сообщений об ошибках |
|--|--|--|--|
| Синтаксические ошибки | Запрос содержит нераспознанные имена, в том числе ссылки на несуществующие операторы, столбцы, функции или таблицы. | Убедитесь в правильности ссылок на [операторы и функции Кусто](https://docs.microsoft.com/azure/data-explorer/kusto/query/) . Проверьте [схему](advanced-hunting-schema-tables.md) для правильных расширенных столбцов поиска, функций и таблиц. Заключите переменные строки в кавычки, чтобы они были распознаны. При написании запросов используйте предложения автозавершения из IntelliSense. | `A recognition error occurred.` |
| Семантические ошибки | В запросе используются допустимые имена оператора, столбца, функции или таблицы, а также ошибки структуры и результирующей логики. В некоторых случаях Расширенный поиск идентифицирует конкретный оператор, который вызвал ошибку. | Проверка на наличие ошибок в структуре запроса. Обратитесь к [документации по Кусто](https://docs.microsoft.com/azure/data-explorer/kusto/query/) за инструкциями. При написании запросов используйте предложения автозавершения из IntelliSense. |  `'project' operator: Failed to resolve scalar expression named 'x'`|
| Время ожидания | Запрос может выполняться только в течение [ограниченного периода, прежде чем истечет время ожидания](advanced-hunting-limits.md). Эта ошибка может происходить чаще при выполнении сложных запросов. | [Оптимизация запроса](advanced-hunting-best-practices.md) | `Query exceeded the timeout period.` |
| Регулирование ресурсов ЦП | В запросах одного клиента превышены [ресурсы ЦП](advanced-hunting-limits.md) , выделенные на основе размера клиента. | Служба проверяет использование ресурсов ЦП каждые 15 минут и ежедневно и отображает предупреждения, если их использование превышает 10% выделенного ограничения. Если вы достигли уровня использования 100%, служба блокирует запросы, пока не будет следующий ежедневный или 15 минутный цикл. [Оптимизация запросов, чтобы избежать попадания в пределы ЦП](advanced-hunting-best-practices.md) | - `This query used X% of your organization's allocated resources for the current 15 minutes.`<br>- `You have exceeded processing resources allocated to this tenant. You can run queries again in <duration>.` |
| Превышено ограничение размера результата  | Суммарный размер набора результатов для запроса превысил максимально допустимое значение. Эта ошибка может возникать, если результирующий набор настолько велик, что усечение в пределах 10 000-записи не может уменьшить его до допустимого размера. Эта ошибка может повлиять на результаты с несколькими столбцами с изменяемым содержимым. | [Оптимизация запроса](advanced-hunting-best-practices.md) | `Result size limit exceeded. Use "summarize" to aggregate results, "project" to drop uninteresting columns, or "take" to truncate results.` |
| Чрезмерное потребление ресурсов | Запрос потребляет чрезмерные объемы ресурсов и был остановлен от завершения. В некоторых случаях Расширенный поиск идентифицирует определенный оператор, который не был оптимизирован. | [Оптимизация запроса](advanced-hunting-best-practices.md) | -`Query stopped due to excessive resource consumption.`<br>-`Query stopped. Adjust use of the <operator name> operator to avoid excessive resource consumption.` |
| Неизвестные ошибки | Не удалось выполнить запрос по неизвестной причине. | Попробуйте выполнить запрос еще раз. Обращение в корпорацию Майкрософт через портал, если запросы продолжают возвращать неизвестные ошибки. | `An unexpected error occurred during query execution. Please try again in a few minutes.`

## <a name="related-topics"></a>Статьи по теме
- [Расширенные рекомендации по поиску](advanced-hunting-best-practices.md)
- [Ограничения службы](advanced-hunting-limits.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Обзор языка запросов Кусто](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
