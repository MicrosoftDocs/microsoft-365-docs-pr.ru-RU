---
title: Обработка ошибок в предварительной охоте для ATP Защитника Microsoft
description: Понимание ошибок, отображаемой при использовании расширенных методов охоты
keywords: продвинутая охота, охота на угрозы, поиск киберугроз, mdatp, microsoft defender atp, wdatp, m365, поиск, запрос, телеметрия, схема, кусто, времяпрепровода, ресурсы, ошибки, неизвестная ошибка
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
ms.openlocfilehash: b27ef34d465832bdf0eee3841385d64158553a6c
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500201"
---
# <a name="handle-advanced-hunting-errors"></a>Обработка ошибок, совершенных в области охоты

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

Расширенный поиск отображает ошибки, чтобы уведомить об ошибках синтаксиса и всякий раз, когда запросы бьют по заранее [.](advanced-hunting-limits.md) В приведенной ниже таблице приведены советы по устранению ошибок или их устранению. 

| Тип "ошибка" | Причина | Решение | Примеры сообщений об ошибке |
|--|--|--|--|
| Ошибки синтаксиса | Запрос содержит неуязвимые имена, включая ссылки на несущестутные операторы, столбцы, функции или таблицы. | Убедитесь, [что ссылки на операторов и функций Kusto](https://docs.microsoft.com/azure/data-explorer/kusto/query/) являются правильными. Проверьте [схему правильных](advanced-hunting-schema-reference.md) расширенных столбцов, функций и таблиц для охоты. Заключив переменные строки в кавычках, чтобы они были признаны. При написании запросов используйте предложения автокомплетов из IntelliSense. | `A recognition error occurred.` |
| Семантические ошибки | Хотя в запросе используются допустимые имена операторов, столбцов, функций или таблиц, в его структуре и логике в результате имеются ошибки. В некоторых случаях передовая охота определяет конкретного оператора, который вызвал ошибку. | Проверьте ошибки в структуре запроса. Обратитесь к [документации Kusto](https://docs.microsoft.com/azure/data-explorer/kusto/query/) для руководства. При написании запросов используйте предложения автокомплетов из IntelliSense. |  `'project' operator: Failed to resolve scalar expression named 'x'`|
| Timeouts | Запрос может запускаться только в течение [ограниченного периода до времени.](advanced-hunting-limits.md) Эта ошибка может происходить чаще при запуске сложных запросов. | [Оптимизация запроса](advanced-hunting-best-practices.md) | `Query exceeded the timeout period.` |
| Регулирование ЦП | Запросы в одном клиенте превысили ресурсы [ЦП,](advanced-hunting-limits.md) выделенные в зависимости от размера клиента. | Служба проверяет использование ресурсов ЦП каждые 15 минут и ежедневно и отображает предупреждения после превышения 10% от выделенного лимита. Если уровень использования достигает 100%, служба блокирует запросы до следующего ежедневного или 15-минутного цикла. [Оптимизация запросов, чтобы избежать ограничения ЦП](advanced-hunting-best-practices.md) | - `This query used X% of your organization's allocated resources for the current 15 minutes.`<br>- `You have exceeded processing resources allocated to this tenant. You can run queries again in <duration>.` |
| Превышено ограничение размера результатов  | Совокупный размер набора результатов для запроса превысил максимальное ограничение. Эта ошибка может возникнуть, если набор результатов настолько велик, что порезка с ограничением в 10 000 записей не может уменьшить его до приемлемого размера. Результаты с несколькими столбцами с большим содержимым с большей вероятностью будут влиять на эту ошибку. | [Оптимизация запроса](advanced-hunting-best-practices.md) | `Result size limit exceeded. Use "summarize" to aggregate results, "project" to drop uninteresting columns, or "take" to truncate results.` |
| Чрезмерное потребление ресурсов | Запрос потреблял чрезмерное количество ресурсов и был остановлен до завершения. В некоторых случаях передовая охота определяет конкретного оператора, который не был оптимизирован. | [Оптимизация запроса](advanced-hunting-best-practices.md) | -`Query stopped due to excessive resource consumption.`<br>-`Query stopped. Adjust use of the <operator name> operator to avoid excessive resource consumption.` |
| Неизвестные ошибки | Запрос не удалось из-за неизвестной причины. | Попробуйте снова запускать запрос. Свяжитесь с Корпорацией Майкрософт через портал, если запросы продолжают возвращать неизвестные ошибки. | `An unexpected error occurred during query execution. Please try again in a few minutes.`

## <a name="related-topics"></a>Статьи по теме
- [Передовые методы охоты](advanced-hunting-best-practices.md)
- [Ограничения службы](advanced-hunting-limits.md)
- [Сведения о схеме](advanced-hunting-schema-reference.md)
- [Обзор языка запросов Kusto](https://docs.microsoft.com/azure/data-explorer/kusto/query/)