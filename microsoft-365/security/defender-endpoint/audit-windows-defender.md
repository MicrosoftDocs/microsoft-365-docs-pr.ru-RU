---
title: Проверка работы функций Microsoft Defender для конечных точек в режиме аудита
description: Режим аудита позволяет увидеть, как Microsoft Defender для конечной точки будет защищать устройства при его включении.
keywords: использование охраны, аудита, аудита, режима, включенного, отключенного, тестирования, демонстрации, оценки, лаборатории
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.topic: article
ms.technology: mde
ms.date: 06/02/2021
ms.openlocfilehash: 23de13e9a2b0fb02b95c9bb367c3fd99e11e89c8
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985100"
---
# <a name="test-attack-surface-reduction-in-microsoft-defender-for-endpoint"></a>Тестирование уменьшения поверхности атаки в Microsoft Defender для конечной точки

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**

- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

В составе группы безопасности организации можно настроить возможности уменьшения поверхности атаки для работы в режиме аудита, чтобы узнать, как они будут работать. В режиме аудита можно включить:

- Правила сокращения направлений атак
- Защита от эксплойтов
- Защита сети
- И управляемый доступ к папкам в режиме аудита

Режим аудита позволяет увидеть запись *того,* что произошло бы, если бы вы включили эту функцию.

Вы можете включить режим аудита при тестировании работы функций. Это поможет убедиться, что ваши бизнес-приложения не затронуты. Вы также можете получить представление о том, сколько попыток изменения подозрительных файлов происходит в течение определенного периода времени.

Эти функции не будут блокировать приложения, скрипты или файлы, которые не будут изменяться. Однако журнал Windows событий будет записывать события, как если бы функции были полностью включены. В режиме аудита можно просмотреть журнал событий, чтобы узнать, какое влияние эта функция имела бы, если бы она была включена.

Чтобы найти проверенные записи, перейдите к приложениям и службам  >  **Microsoft**  >  **Windows**  >  **Защитник Windows**  >  **Operational.**

Используйте Defender для конечной точки, чтобы получить более подробные сведения для каждого события, особенно для исследования правил уменьшения поверхности атаки. Использование консоли Defender для конечной точки позволяет исследовать проблемы в рамках временной шкалы оповещений [и сценариев расследования.](investigate-alerts.md)

Режим аудита можно включить с помощью поставщиков групповой политики, PowerShell и служб конфигурации (CSP).

> [!TIP]
> Вы также можете посетить веб-Защитник Windows [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) тестового поля в demo.wd.microsoft.com, чтобы подтвердить, что функции работают, и посмотреть, как они работают.

| Параметры аудита | Как включить режим аудита | Просмотр событий |
|---------|---------|---------|
| Аудит применяется ко всем событиям | [Включить контролируемый доступ к папкам](enable-controlled-folders.md) | [События доступа к управляемым папкам](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| Аудит применяется к отдельным правилам | [Включить правила сокращения направлений атак](enable-attack-surface-reduction.md) | [События правила уменьшения поверхности атаки](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| Аудит применяется ко всем событиям | [Включить защиту сети](enable-network-protection.md) | [События защиты сети](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| Аудит применяется к отдельным смягчам | [Включить защиту от эксплойтов](enable-exploit-protection.md) | [События защиты эксплойтов](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)
