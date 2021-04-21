---
title: Исследование событий подключения, происходящих за прокси-серверами переадресации.
description: Узнайте, как использовать расширенный мониторинг уровня HTTP с помощью защиты сети в Microsoft Defender для конечной точки, которая является реальной целью, а не прокси-сервером.
keywords: прокси, защита сети, прокси-серверы, сетевые события, аудит, блок, доменные имена, домен
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 47be07759a72a080a3687ed3bb50cef9d0a959b7
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904050"
---
# <a name="investigate-connection-events-that-occur-behind-forward-proxies"></a>Исследование событий подключения, происходящих за прокси-серверами переадресации.

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatemachines-abovefoldlink)

Defender for Endpoint поддерживает мониторинг сетевого подключения с разных уровней сетевого стека. Сложный случай, когда сеть использует прокси-сервер в качестве шлюза в Интернет.

Прокси-сервер действует так, как если бы это была целевая конечная точка.  В этих случаях простые мониторы сетевого подключения проверяют подключение к прокси-серверу, который является правильным, но имеет более низкое значение для исследования. 

Defender for Endpoint поддерживает расширенный мониторинг уровня HTTP с помощью защиты сети. При включенном включаемом событии всплыл новый тип события, который предоставляет реальные целевые доменные имена.

## <a name="use-network-protection-to-monitor-network-connection-behind-a-firewall"></a>Защита сети для мониторинга сетевого подключения за брандмауэром
Мониторинг сетевого подключения за прокси-сервером можно за счет дополнительных сетевых событий, происходящих из защиты сети. Чтобы увидеть их на временной шкале устройства, включим защиту сети (как минимум в режиме аудита). 

Защита сети можно контролировать с помощью следующих режимов:

- **Блокировка** <br> Пользователям или приложениям будет заблокировано подключение к опасным доменам. Вы сможете увидеть это действие в Центре безопасности Защитника Майкрософт.
- **Audit** <br> Пользователям или приложениям не будет заблокировано подключение к опасным доменам. Однако вы все равно увидите это действие в Центре безопасности Защитника Майкрософт.


Если отключить защиту сети, пользователям или приложениям не будет заблокировано подключение к опасным доменам. Вы не увидите сетевой активности в Центре безопасности Microsoft Defender.

Если его не настроить, блокировка сети будет отключена по умолчанию.

Дополнительные сведения см. в [дополнительных сведениях о защите сети.](enable-network-protection.md)

## <a name="investigation-impact"></a>Влияние на исследование
Когда включена защита сети, вы увидите, что на временной шкале устройства IP-адрес будет представлять прокси-сервер, а реальный целевой адрес будет показан.

![Изображение сетевых событий на временной шкале устройства](images/atp-proxy-investigation.png)

Дополнительные события, запускаемые на уровне защиты сети, теперь доступны для поверхности реальных имен домена даже за прокси-сервером.

Сведения о событии:

![Изображение единого сетевого события](images/atp-proxy-investigation-event.png)



## <a name="hunt-for-connection-events-using-advanced-hunting"></a>Поиск событий подключения с помощью расширенных методов охоты 
Все новые события подключения доступны для вас, чтобы охотиться на с помощью расширенных охоты, а также. Так как эти события являются событиями подключения, их можно найти в таблице DeviceNetworkEvents под `ConnecionSuccess` типом действия.

С помощью этого простого запроса вы сможете показать все соответствующие события:

```
DeviceNetworkEvents
| where ActionType == "ConnectionSuccess" 
| take 10
```

![Изображение запроса на расширенный запрос на охоту](images/atp-proxy-investigation-ah.png)

Можно также отфильтровать события, связанные с подключением к самому прокси-серверу. 

Для фильтрации подключений к прокси-серверу используйте следующий запрос:

```
DeviceNetworkEvents
| where ActionType == "ConnectionSuccess" and RemoteIP != "ProxyIP"  
| take 10
```



## <a name="related-topics"></a>Похожие темы
- [Применение защиты сети с помощью GP - CSP политики](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection)
