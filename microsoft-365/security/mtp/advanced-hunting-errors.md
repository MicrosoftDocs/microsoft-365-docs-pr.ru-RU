---
title: Обработка ошибок в advanced hunting for Microsoft 365 Defender
description: Понимание ошибок, отображаемой при использовании расширенных методов охоты
keywords: расширенный поиск, охота на угрозы, поиск киберугроз, защита от угроз (Майкрософт), Microsoft 365, mtp, m365, поиск, запрос, телеметрия, схема, kusto, время выполнения, ресурсы, ошибки, неизвестная ошибка, ограничения, квота, параметр, выделение
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
ms.openlocfilehash: 645e78de9d7a8a779be8741a7471e9c1a88ba538
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929650"
---
# <a name="handle-advanced-hunting-errors"></a>Обработка ошибок расширенных поисков

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Расширенный поиск отображает ошибки для уведомления о синтаксисе ошибок и при попадании запросов в предварительно определенные квоты и [параметры использования.](advanced-hunting-limits.md) Советы по устранению или устранению ошибок см. в таблице ниже.

| Тип "ошибка" | Причина | Решение | Примеры сообщений об ошибках |
|--|--|--|--|
| Ошибки синтаксиса | Запрос содержит невыявленные имена, включая ссылки на несущестовые операторы, столбцы, функции или таблицы. | Убедитесь, [что ссылки на операторы и](https://docs.microsoft.com/azure/data-explorer/kusto/query/) функции Kusto верны. Проверьте [схему на правильности](advanced-hunting-schema-tables.md) столбцов, функций и таблиц для расширенных поисков. Заключив переменные строки в кавычках, чтобы они распознались. При написании запросов используйте предложения автозаполнеия из IntelliSense. | `A recognition error occurred.` |
| Семантические ошибки | Хотя в запросе используются допустимые имена операторов, столбцов, функций или таблиц, в его структуре и итоговой логике имеются ошибки. В некоторых случаях расширенный поиск определяет определенный оператор, который вызвал ошибку. | Проверьте ошибки в структуре запроса. Инструкции [можно найти в документации Kusto.](https://docs.microsoft.com/azure/data-explorer/kusto/query/) При написании запросов используйте предложения автозаполнеия из IntelliSense. |  `'project' operator: Failed to resolve scalar expression named 'x'`|
| Timeouts | Запрос может запускаться только в течение [ограниченного периода времени, прежде чем будет отсюме.](advanced-hunting-limits.md) Эта ошибка может происходить чаще при запуске сложных запросов. | [Оптимизация запроса](advanced-hunting-best-practices.md) | `Query exceeded the timeout period.` |
| Регулирование ЦП | Запросы в том же клиенте превысили ресурсы [ЦП,](advanced-hunting-limits.md) выделенные в зависимости от размера клиента. | Служба проверяет использование ресурсов ЦП каждые 15 минут и ежедневно и отображает предупреждения, когда использование превышает 10 % от выделенной квоты. Если уровень использования достигает 100 %, служба блокирует запросы до следующего ежедневного или 15-минутного цикла. [Оптимизация запросов во избежание попадания в квоты ЦП](advanced-hunting-best-practices.md) | - `This query used X% of your organization's allocated resources for the current 15 minutes.`<br>- `You have exceeded processing resources allocated to this tenant. You can run queries again in <duration>.` |
| Превышено ограничение на размер результатов  | Общий размер набора результатов для запроса превысил максимальный размер. Эта ошибка может возникнуть, если набор результатов настолько велик, что обрезка с ограничением в 10 000 записей не может уменьшить ее до приемлемого размера. Эта ошибка с большей вероятностью повлияет на результаты с несколькими столбцами с содержимым с возможностью изменения. | [Оптимизация запроса](advanced-hunting-best-practices.md) | `Result size limit exceeded. Use "summarize" to aggregate results, "project" to drop uninteresting columns, or "take" to truncate results.` |
| Чрезмерное потребление ресурсов | Запрос потреблял слишком много ресурсов и был остановлен. В некоторых случаях расширенный поиск определяет определенный оператор, который не был оптимизирован. | [Оптимизация запроса](advanced-hunting-best-practices.md) | -`Query stopped due to excessive resource consumption.`<br>-`Query stopped. Adjust use of the <operator name> operator to avoid excessive resource consumption.` |
| Неизвестные ошибки | Сбой запроса по неизвестной причине. | Попробуйте снова запускать запрос. Обратитесь в корпорацию Майкрософт через портал, если запросы продолжают возвращать неизвестные ошибки. | `An unexpected error occurred during query execution. Please try again in a few minutes.`

## <a name="related-topics"></a>Связанные статьи
- [Расширенные методы охоты](advanced-hunting-best-practices.md)
- [Квоты и параметры использования](advanced-hunting-limits.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Обзор языка запросов Kusto](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
