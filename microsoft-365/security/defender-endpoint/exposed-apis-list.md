---
title: Поддерживаемые API-API Microsoft Defender для конечных точек
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
ms.openlocfilehash: 77491620f7efa88f8ab249c2b76cd2532ba679dd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198330"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a>Поддерживаемые API-API Microsoft Defender для конечных точек

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)

- Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

## <a name="endpoint-uri-and-versioning"></a>URI конечной точки и версия

### <a name="endpoint-uri"></a>URI конечной точки:            

> База служб URI: https://api.securitycenter.microsoft.com
> 
> На основе OData запросов имеется префикс "/api". Например, для получения оповещений можно отправить запрос GET в https://api.securitycenter.microsoft.com/api/alerts

### <a name="versioning"></a>Версия:

> API поддерживает версию.
> 
> Текущая версия **— V1.0.**
> 
> Чтобы использовать определенную версию, используйте этот формат: `https://api.securitycenter.microsoft.com/api/{Version}` . Пример: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`
> 
> Если вы не указываете версию (например, https://api.securitycenter.microsoft.com/api/alerts ) вы получите последнюю версию.


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


Дополнительные сведения об отдельных поддерживаемых сущностях, в которых можно запускать вызовы API, а также сведения, такие как значения запросов HTTP, заглавные заголовки запросов и ожидаемые ответы.

## <a name="in-this-section"></a>В этом разделе

Статья | Описание
:---|:---
Расширенный охота | Выполнение запросов из API.
Оповещения | Запустите вызовы API, такие как получения оповещений, создания оповещений, обновления оповещений и других.
Домены | Запустите вызовы API, такие как получить устройства, связанные с доменом, статистику домена и другие.
Files | Запустите вызовы API, такие как получения данных о файлах, связанных с файлами оповещений, устройств, связанных с файлами, и статистики файлов.
IPs | Запустите вызовы API, такие как получения оповещений, связанных с IP, и получения статистики IP.
Компьютеры | Запустите вызовы API, такие как получить устройства, получить устройства по ID, сведения о в журнале пользователей, изменить теги и другие.
Действия машины | Запустите вызов API, например Isolation, запустите антивирусное сканирование и другие.
Индикаторы | Запустите вызов API, например создать индикатор, получить Индикаторы и удалить Индикаторы.
Users | Запуск вызовов API, например получения оповещений, связанных с пользователем, и устройств, связанных с пользователем.
Оценка | Запустите вызовы API, такие как получить оценку экспозиции или получить безопасную оценку устройства.
Программное обеспечение | Запустите вызовы API, такие как уязвимости списка с помощью программного обеспечения.
Уязвимость | Запустите вызовы API, такие как устройства списка по уязвимости.
Рекомендация | Запустите вызовы API, такие как Get recommendation by ID.

## <a name="see-also"></a>См. также
- [Microsoft Defender для API конечных точек](apis-intro.md)
