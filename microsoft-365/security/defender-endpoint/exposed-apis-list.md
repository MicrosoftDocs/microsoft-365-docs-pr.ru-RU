---
title: Поддерживаемые API Microsoft Defender для конечной точки
ms.reviewer: ''
description: Узнайте о конкретных поддерживаемых сущностям Microsoft Defender для конечных точек, куда можно создавать вызовы API.
keywords: apis, поддерживаемые apis, actor, alerts, device, user, domain, ip, file, advanced queries, advanced hunting
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 656aa26d80db73bfc52511f9dd94e58e771f3ac6
ms.sourcegitcommit: 9063c7a50a1d7dd6d2e1ca44f53d3c26f21f4ae8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2021
ms.locfileid: "52073839"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a>Поддерживаемые API Microsoft Defender для конечной точки

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)

- Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="endpoint-uri-and-versioning"></a>URI конечной точки и версия

### <a name="endpoint-uri"></a>URI конечной точки

> База служб URI: [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)
>
> На основе OData запросов имеется префикс "/api". Например, для получения оповещений можно отправить запрос GET в [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)

### <a name="versioning"></a>Управление версиями

> API поддерживает версию.
>
> Текущая версия **— V1.0.**
>
> Чтобы использовать определенную версию, используйте этот формат: `https://api.securitycenter.microsoft.com/api/{Version}` . Пример: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`
>
> Если вы не указываете версию (например, `https://api.securitycenter.microsoft.com/api/alerts` ) вы получите последнюю версию.

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Дополнительные сведения об отдельных поддерживаемых сущностях, в которых можно запускать вызовы API, а также сведения, такие как значения запросов HTTP, заглавные заголовки запросов и ожидаемые ответы.

## <a name="in-this-section"></a>В этом разделе

Статья | Описание
:---|:---
[Расширенная охота](run-advanced-query-api.md) | Выполнение запросов из API.
[Методы и свойства оповещений](alerts.md) | Запустите вызовы API, такие как \- получения оповещений, создания оповещений, обновления оповещений и других.
[Автоматизированные методы и свойства исследования](investigation.md) | Запустите вызовы API, такие \- как сбор данных исследования.
[Получать оповещения, связанные с доменом](get-domain-related-alerts.md) | Запустите вызовы API, такие как получить устройства, связанные с \- доменом, статистику домена и другие.
[Методы и свойства файла](files.md) | Запустите вызовы API, такие как получения данных о файлах, связанных с файлами оповещений, устройств, связанных с \- файлами, и статистики файлов.
[Методы и свойства индикаторов](ti-indicator.md) | Запустите вызов API, например \- получить индикаторы, создать индикатор и удалить Индикаторы.
[Получать оповещения, связанные с протоколами IP](get-ip-related-alerts.md) | Запустите вызовы API, такие как получения оповещений, связанных с \- IP, и получения статистики IP.
[Методы и свойства компьютера](machine.md) | Запустите вызовы API, такие как получить устройства, получить устройства по ID, сведения о в журнале \- пользователей, изменить теги и другие.
[Методы и свойства действия компьютера](machineaction.md) | Запустите вызов API, например \- Isolation, запустите антивирусное сканирование и другие.
[Методы и свойства рекомендаций](recommendation.md) | Запустите вызовы API, такие \- как получить рекомендации по ID.
[Методы и свойства оценки](score.md) | Запустите вызовы API, такие \- как получить оценку экспозиции или получить безопасную оценку устройства.
[Методы и свойства программного обеспечения](software.md) | Запустите вызовы API, такие \- как уязвимости списка с помощью программного обеспечения.
[Методы пользователя](user.md) | Запуск вызовов API, например получения оповещений, связанных с \- пользователем, и устройств, связанных с пользователем.
[Методы и свойства уязвимости](vulnerability.md) | Запустите вызовы API, такие как \- устройства списка по уязвимости.

## <a name="see-also"></a>См. также

- [Microsoft Defender для API конечных точек](apis-intro.md)

- [Заметки о выпуске API для Защитника Майкрософт для конечной точки](api-release-notes.md)
