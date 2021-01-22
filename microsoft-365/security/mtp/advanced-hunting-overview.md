---
title: Обзор — расширенный поиск
description: В статье рассказывается о запросах расширенного выслеживания в Microsoft 365 и о том, как их использовать для профилактического обнаружения угроз и слабых мест в своей сети.
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, custom detections, schema, kusto, microsoft 365, Microsoft Threat Protection
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
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 8fbf9c3d93434ec2dbc3f069bc0fbd3fe03fc260
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932278"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-365-defender"></a>Упреждающий поиск угроз с помощью расширенных поисков в Защитнике Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

> Хотите испытать Microsoft 365 Defender? Вы можете [оценить его в лабораторной среде](https://aka.ms/mtp-trial-lab) или запустить [пилотный проект в производственной среде.](https://aka.ms/m365d-pilotplaybook)
>

Расширенное выслеживание— это средство для выслеживания угроз на основе запросов, которое позволяет изучать необработанные данные за период до 30 дней. Вы можете заблаговременно проверять события в сети на обнаружение индикаторов угроз и сущностями. Гибкий доступ к данным обеспечивает неоконченную охоту как на известные, так и на потенциальные угрозы.
<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

Вы можете использовать одни и те же запросы на поиск угроз для создания пользовательских правил обнаружения. Эти правила запускаются автоматически для проверки и реагирования на подозрительные нарушения безопасности, неправильного выбора компьютеров и других результатов.

Эта возможность похожа на расширенный поиск [в Microsoft Defender для конечной точки.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) Эта возможность доступна в Центре безопасности Microsoft 365 и поддерживает запросы, которые проверяют более широкий набор данных из:

- Microsoft Defender для конечной точки
- Microsoft Defender для Office 365
- Microsoft Cloud App Security
- Microsoft Defender для удостоверений

Чтобы использовать расширенный поиск, [включите Microsoft 365 Defender.](mtp-enable.md)

## <a name="get-started-with-advanced-hunting"></a>Начало работы с расширенным выслеживанием

Для быстрого начала работы с расширенным поиском рекомендуется предпринять несколько действий.

| Цель обучения | Описание | Ресурс |
|--|--|--|
| **Изучите язык** | Расширенный поиск основан на языке запросов [Kusto,](https://docs.microsoft.com/azure/kusto/query/)поддерживающих один и тот же синтаксис и операторы. Начать изучение языка запросов можно, выполнив свой первый запрос. | [Сведения о языке запросов](advanced-hunting-query-language.md) |
| **Узнайте, как использовать результаты запроса** | Узнайте о диаграммах и различных способах просмотра или экспорта результатов. Узнайте, как быстро оптимизировать запросы, получить более подробную информацию и принять ответные действия. | - [Работа с результатами запроса](advanced-hunting-query-results.md)<br>- [Действие с результатами запроса](advanced-hunting-take-action.md) |
| **Сведения о схеме** | Формирование четкого и глубокого представления о таблицах схемы и входящих в них столбцах. Узнайте, где искать данные при построении запросов. | - [Справочник по схеме](advanced-hunting-schema-tables.md)<br>- [Переход с Microsoft Defender на конечную точку](advanced-hunting-migrate-from-mdatp.md) |
| **Советы и примеры для экспертов** | Бесплатное обучение с помощью руководств от экспертов Майкрософт. Возможен поиск в коллекции предварительно настроенных запросов для использования при разных сценариев выслеживания угроз. | - [Получите экспертное обучение](advanced-hunting-expert-training.md)<br>- [Использование общих запросов](advanced-hunting-shared-queries.md)<br>- [Go hunt](advanced-hunting-go-hunt.md)<br>- [Поиск угроз на различных устройствах, электронных письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md) |
| **Оптимизация запросов и обработка ошибок** | В этой теме вы знаете, как создавать эффективные запросы без ошибок. | - [Практические методики запроса](advanced-hunting-best-practices.md)<br>- [Обработка ошибок](advanced-hunting-errors.md) |
| **Создание пользовательских правил обнаружения** | В этой теме поймут, как можно использовать расширенные поисковые запросы для запуска оповещений и автоматического реагирования на них. | - [Обзор пользовательских обнаружений](custom-detections-overview.md)<br>- [Настраиваемые правила обнаружения](custom-detection-rules.md) |

## <a name="get-access"></a>Получить доступ
Чтобы использовать расширенный поиск или другие возможности [Защитника Microsoft 365,](microsoft-threat-protection.md) необходима соответствующая роль в Azure Active Directory. Кроме того, доступ к данным конечной точки определяется с помощью параметров управления доступом на основе ролей (RBAC) в Microsoft Defender для конечной точки. [Узнайте об управлении доступом к Microsoft 365 Defender](mtp-permissions.md)

## <a name="data-freshness-and-update-frequency"></a>Свежесть и частота обновления данных
Данные advanced hunting можно классифицируются на два отдельных типа, каждый из которых консолидируется по-разному.

- **Данные о событиях или** действиях — заполнение таблиц оповещений, событий безопасности, системных событий и регулярных оценок. Расширенный поиск получает эти данные почти сразу после того, как датчики, которые их собирают, успешно передают их в соответствующие облачные службы. Например, вы можете запрашивать данные событий от работоустанавливных датчиков на рабочих станциях или контроллерах домена почти сразу после того, как они будут доступны в Microsoft Defender для endpoint и Microsoft Defender для удостоверений.
- **Данные сущности —** заполняют таблицы сведениями о пользователях и устройствах. Эти данные приходят как из относительно статических источников данных, так и из динамических источников, таких как записи Active Directory и журналы событий. Для предоставления новых данных таблицы обновляются каждые 15 минут, добавляя строки, которые могут быть заполнены не полностью. Каждые 24 часа данные консолидированы для вставки записи, которая содержит последний, наиболее полный набор данных о каждом объекте.

## <a name="time-zone"></a>Часовой пояс
Сведения о времени в advanced hunting находится в часовом поясе UTC.

## <a name="related-topics"></a>См. также
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Учебные курсы для экспертов](advanced-hunting-expert-training.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
- [Обзор настраиваемых обнаружений](custom-detections-overview.md)

