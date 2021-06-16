---
title: Оценка защиты сети
description: Узнайте, как работает защита сети, протестуя распространенные сценарии, от которые она защищает.
keywords: Защита сети, эксплойтов, вредоносный веб-сайт, IP, домен, домены, оценка, тестирование, демонстрация
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
ms.topic: conceptual
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 03d05966401c8f3a8bdcec413e85c9a6d2a3ec5c
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926575"
---
# <a name="evaluate-network-protection"></a>Оценка защиты сети

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)
- - [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[Защита сети](network-protection.md) позволяет сотрудникам не использовать любое приложение для доступа к опасным доменам, в которые могут быть организованы фишинговые атаки, эксплойты и другой вредоносный контент в Интернете.

В этой статье вы можете оценить защиту сети, включив функцию и направляя ее на сайт тестирования. Сайты в этой статье оценки не являются вредоносными. Это специально созданные веб-сайты, которые притворяются вредоносными. Сайт будет реплицировать поведение, которое произойдет, если пользователь посетил вредоносный сайт или домен.

> [!TIP]
> Вы также можете посетить веб-сайт тестового поля Защитника Майкрософт demo.wd.microsoft.com, чтобы узнать, как работают другие функции защиты. [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)

## <a name="enable-network-protection-in-audit-mode"></a>Включить защиту сети в режиме аудита

Включить защиту сети в режиме аудита, чтобы узнать, какие IP-адреса и домены были бы заблокированы. Вы можете убедиться, что это не влияет на бизнес-приложения, или получить представление о том, как часто возникают блоки.

1. Введите **powershell** в меню Пуск, щелкните правой кнопкой мыши **Windows PowerShell** выберите **Выполнить в качестве администратора**
2. Введите следующий cmdlet:

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

### <a name="visit-a-fake-malicious-domain"></a>Посетите (поддельный) вредоносный домен

1. Откройте Internet Explorer, Google Chrome или любой другой браузер по вашему выбору.

1. Перейдите по ссылке [https://smartscreentestratings2.net](https://smartscreentestratings2.net).

Подключение к сети будет разрешено, и будет отображаться тестовая сообщение.

![Например, уведомление о блокировке подключения: администратор ИТ-Безопасность Windows заблокировать это сетевое подключение. Свяжитесь со своей службой поддержки ИТ.](/microsoft-365/security/defender-endpoint/images/np-notif)

## <a name="review-network-protection-events-in-windows-event-viewer"></a>Просмотр событий защиты сети в Windows просмотра событий

Чтобы просмотреть заблокированные приложения, откройте viewer событий и фильтр для event ID 1125 в журнале Microsoft-Windows-Windows-Defender/Operational. В следующей таблице перечислены все события защиты сети.

| Идентификатор события | Provide/Source | Описание |
|-|-|-|
|5007 | Защитник Windows (оперативная) | Событие при смене параметров |
|1125 | Защитник Windows (оперативная) | Событие при аудите сетевого подключения |
|1126 | Защитник Windows (оперативная) | Событие, когда сетевое подключение заблокировано |

## <a name="see-also"></a>См. также

* [Защита сети](network-protection.md)
* [Включить защиту сети](enable-network-protection.md)
* [Защита сети от неполадок](troubleshoot-np.md)
