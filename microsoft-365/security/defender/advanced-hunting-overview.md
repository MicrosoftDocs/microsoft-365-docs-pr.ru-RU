---
title: Обзор — расширенный поиск
description: В статье рассказывается о запросах расширенного выслеживания в Microsoft 365 и о том, как их использовать для профилактического обнаружения угроз и слабых мест в своей сети.
keywords: передовая охота, охота на угрозы, охота на киберугрозы, Microsoft 365 Defender, Microsoft 365, m365, поиск, запрос, телеметрия, настраиваемые обнаружения, схема, кусто
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: f43d3bf9575f00649a2b5015a8be16351bebd11b
ms.sourcegitcommit: 9063c7a50a1d7dd6d2e1ca44f53d3c26f21f4ae8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2021
ms.locfileid: "52073965"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-365-defender"></a>Активная охота на угрозы с расширенным поиском в Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

> Хотите попробовать Microsoft 365 Defender? Вы можете [оценить его в лабораторной среде](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) или [запустить пилотный проект в производственной среде](m365d-pilot.md?ocid=cx-evalpilot).
>

Расширенное выслеживание— это средство для выслеживания угроз на основе запросов, которое позволяет изучать необработанные данные за период до 30 дней. Вы можете упреждающий осмотр событий в сети, чтобы найти индикаторы и объекты угрозы. Гибкий доступ к данным позволяет безудержно искать как известные, так и потенциальные угрозы.
<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

Вы можете использовать одни и те же запросы на поиск угроз для создания пользовательских правил обнаружения. Эти правила запускаются автоматически для проверки и реагирования на предполагаемые нарушения, неправильного устройства и других выводов.

Эта возможность аналогична продвинутой охоте [в Microsoft Defender для конечной точки.](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) Эта Microsoft 365 поддерживает запросы, которые проверяют более широкий набор данных из:

- Microsoft Defender для конечной точки
- Microsoft Defender для Office 365
- Microsoft Cloud App Security
- Microsoft Defender для удостоверений

Чтобы использовать передовую охоту, [включи Microsoft 365 Defender](m365d-enable.md).

## <a name="get-started-with-advanced-hunting"></a>Начало работы с расширенным выслеживанием

Мы рекомендуем пройти несколько этапов, чтобы быстро начать работу с расширенным поиском.

| Цель обучения | Описание | Ресурс |
|--|--|--|
| **Выучат язык** | Advanced hunting is based on [Kusto query language,](/azure/kusto/query/)supporting the same syntax and operators. Начать изучение языка запросов можно, выполнив свой первый запрос. | [Сведения о языке запросов](advanced-hunting-query-language.md) |
| **Узнайте, как использовать результаты запроса** | Узнайте о диаграммах и различных способах просмотра или экспорта результатов. Узнайте, как быстро настроить запросы, разверлить, чтобы получить более подробную информацию, и принять меры реагирования. | - [Работа с результатами запроса](advanced-hunting-query-results.md)<br /> - [Действие по результатам запроса](advanced-hunting-take-action.md) |
| **Сведения о схеме** | Формирование четкого и глубокого представления о таблицах схемы и входящих в них столбцах. Узнайте, где искать данные при построении запросов. | - [Ссылка на схему](advanced-hunting-schema-tables.md) <br />- [Переход от Microsoft Defender для конечной точки](advanced-hunting-migrate-from-mde.md) |
| **Получить советы и примеры экспертов** | Обучение бесплатно с помощью руководств от экспертов Майкрософт. Возможен поиск в коллекции предварительно настроенных запросов для использования при разных сценариев выслеживания угроз. | - [Обучение экспертов](advanced-hunting-expert-training.md) <br />- [Использование общих запросов](advanced-hunting-shared-queries.md) <br />- [Go hunt](advanced-hunting-go-hunt.md) <br />- [Поиск угроз на устройствах, электронной почте, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md) |
| **Оптимизация запросов и обработка ошибок** | Понять, как создавать эффективные и без ошибок запросы. | - [Наилучшие методы запроса](advanced-hunting-best-practices.md)<br />- [Обработка ошибок](advanced-hunting-errors.md) |
| **Создание настраиваемой системы обнаружения** | Понимание того, как можно использовать расширенные запросы на охоту для запуска оповещений и автоматически принимать ответные действия. | - [Пользовательский обзор обнаружения](custom-detections-overview.md) <br />- [Настраиваемые правила обнаружения](custom-detection-rules.md) |

## <a name="get-access"></a>Получить доступ
Чтобы использовать расширенные возможности [Microsoft 365 Defender,](microsoft-365-defender.md) вам потребуется соответствующая роль в Azure Active Directory. [Ознакомьтесь с требуемой ролью и разрешениями для предварительной охоты.](custom-roles.md)

Кроме того, доступ к данным конечной точки определяется настройками управления доступом на основе ролей (RBAC) в Microsoft Defender for Endpoint. [Узнайте об управлении доступом к Microsoft 365 Defender](m365d-permissions.md).


## <a name="data-freshness-and-update-frequency"></a>Свежесть данных и частота обновления
Расширенные данные охоты можно классифицируется на два различных типа, каждый из которых консолидируется по-разному.

- **Данные событий или действий** заполняют таблицы оповещений, событий безопасности, системных событий и обычных оценок. Расширенный поиск получает эти данные практически сразу после того, как собранные ими датчики успешно передают их в соответствующие облачные службы. Например, вы можете запрашивать данные о событиях с здоровых датчиков на рабочих станциях или контроллерах домена почти сразу после того, как они будут доступны в Microsoft Defender for Endpoint и Microsoft Defender for Identity.
- **Данные Entity** заполняют таблицы сведениями о пользователях и устройствах. Эти данные приходят как из относительно статических источников данных, так и из динамических источников, таких как записи Active Directory и журналы событий. Чтобы предоставить свежие данные, таблицы обновляются каждые 15 минут, добавляя строки, которые могут быть заполнены не полностью. Каждые 24 часа данные консолидированы, чтобы вставить запись, содержающую последний, наиболее полный набор данных о каждом объекте.

## <a name="time-zone"></a>Часовой пояс
Сведения о времени в продвинутой охоте в часовом поясе UTC.

## <a name="related-topics"></a>См. также
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Учебные курсы для экспертов](advanced-hunting-expert-training.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Применение рекомендаций по использованию запросов](advanced-hunting-best-practices.md)
- [Обзор настраиваемых обнаружений](custom-detections-overview.md)
