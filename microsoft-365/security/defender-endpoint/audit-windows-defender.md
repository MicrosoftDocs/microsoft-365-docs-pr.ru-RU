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
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7ce652d58be2d9ff28d82c088d5471a7bffdf6dc
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570976"
---
# <a name="test-how-microsoft-defender-for-endpoint-features-work-in-audit-mode"></a>Проверка работы функций Microsoft Defender для конечных точек в режиме аудита

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


Вы можете включить правила уменьшения поверхности атаки, защиту от эксплойтов, защиту сети и контролируемый доступ к папкам в режиме аудита. Режим аудита позволяет увидеть запись *того,* что произошло бы, если бы вы включили эту функцию.

При тестировании работы функций в организации может потребоваться включить режим аудита. Это поможет убедиться, что ваши бизнес-приложения не затронуты. Вы также можете получить представление о том, сколько попыток изменения подозрительных файлов происходит в течение определенного периода времени.

Эти функции не будут блокировать приложения, скрипты или файлы, которые не будут изменяться. Однако журнал событий Windows будет записывать события так, как если бы функции были полностью включены. В режиме аудита можно просмотреть журнал событий, чтобы узнать, какое влияние эта функция оказала бы, если бы она была включена.

Чтобы найти проверенные записи, перейдите к **приложениям** и службам  >  **Microsoft**  >  **Windows**  >  **Защитник Windows**  >  **Operational.**

Вы можете использовать Defender для конечной точки, чтобы получить более подробные сведения для каждого события, особенно для исследования правил уменьшения поверхности атаки. Использование консоли Defender для конечной точки позволяет исследовать проблемы в рамках временной шкалы оповещений [и сценариев расследования.](investigate-alerts.md)

Чтобы включить режим аудита, можно использовать поставщики групповых политик, PowerShell и служб конфигурации (CSP).

> [!TIP]
> Вы также можете посетить веб Защитник Windows [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) тестовом сайте demo.wd.microsoft.com, чтобы подтвердить, что функции работают, и посмотреть, как они работают.

 **Параметры аудита** | **Как включить режим аудита** | **Просмотр событий**
|---------|---------|---------|
| Аудит применяется ко всем событиям | [Включить контролируемый доступ к папкам](enable-controlled-folders.md) | [События доступа к управляемым папкам](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| Аудит применяется к отдельным правилам | [Включить правила сокращения направлений атак](enable-attack-surface-reduction.md) | [События правила уменьшения поверхности атаки](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| Аудит применяется ко всем событиям | [Включить защиту сети](enable-network-protection.md) | [События защиты сети](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| Аудит применяется к отдельным смягчам | [Включить защиту от эксплойтов](enable-exploit-protection.md) | [События защиты эксплойтов](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)

## <a name="related-topics"></a>Статьи по теме

* [Защита устройств от эксплойтов](exploit-protection.md)
* [Уменьшение поверхностей атаки с помощью правил уменьшения поверхности атаки](attack-surface-reduction.md)
* [Защита сети](network-protection.md)
* [Защита важных папок](controlled-folders.md)
