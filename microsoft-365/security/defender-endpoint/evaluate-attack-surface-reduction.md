---
title: Оценка правил сокращения направлений атак
description: Узнайте, как уменьшение поверхности атаки блокирует и предотвращает атаки с помощью настраиваемой демонстрации.
keywords: Уменьшение поверхности атаки, бедра, система предотвращения вторжений на хост, правила защиты, антиэкспозиция, антиэкспплойт, эксплойт, профилактика инфекции, оценка, тестирование, демонстрация
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.topic: article
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 5d3cd7893af4c91807782c269231a280b413733e
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861230"
---
# <a name="evaluate-attack-surface-reduction-rules"></a>Оценка правил сокращения направлений атак

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

Правила уменьшения поверхности атаки помогают предотвратить действия, обычно используемые вредоносными программами для компрометации устройств или сетей. Правила уменьшения поверхности атаки помогают закрыть многие из общих точек входа, используемых вредоносными программами и программами-вымогателями. 

Установите правила уменьшения поверхности атаки для устройств, работающих с любыми из следующих выпусков и версий Windows:

- Windows 10 Pro версии [1709](/windows/whats-new/whats-new-windows-10-version-1709) или более поздней версии
- Windows 10 Корпоративная версии [1709](/windows/whats-new/whats-new-windows-10-version-1709) или более поздней версии
- Windows Сервер, [версия 1803 (полугодовой канал)](/windows-server/get-started/whats-new-in-windows-server-1803) или более поздний
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

> [!WARNING]
> Включение правил снижения службы атаки на Windows Server 2016 может привести к неожиданным результатам и производительности сервера. Мы не рекомендуем включать или развернуть правила уменьшения поверхности атаки на неподключаемой платформе.

Узнайте, как оценить правила уменьшения поверхности атаки, включив режим аудита для тестирования функции непосредственно в организации.

> [!TIP]
> Вы также можете посетить веб-сайт демонстрационных сценариев Microsoft Defender for Endpoint в demo.wd.microsoft.com, чтобы подтвердить, что функция работает, и посмотреть, как она работает. [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)

## <a name="use-audit-mode-to-measure-impact"></a>Использование режима аудита для измерения воздействия

Включай правила уменьшения поверхности атаки в режиме аудита, чтобы просмотреть запись приложений, которые были бы заблокированы, если бы функция была полностью включена. Проверьте, как эта функция будет работать в организации, чтобы убедиться, что она не влияет на ваши бизнес-приложения. Вы также можете получить представление о том, как часто правила будут работать при нормальном использовании.

Чтобы включить правило уменьшения поверхности атаки в режиме аудита, используйте следующий cmdlet PowerShell:

```PowerShell
Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
```

Где значение GUID правила уменьшения поверхности `<rule ID>` [атаки.](attack-surface-reduction.md#attack-surface-reduction-rules)

Чтобы включить все добавленные правила уменьшения поверхности атаки в режиме аудита, используйте следующий cmdlet PowerShell:

```PowerShell
(Get-MpPreference).AttackSurfaceReductionRules_Ids | Foreach {Add-MpPreference -AttackSurfaceReductionRules_Ids $_ -AttackSurfaceReductionRules_Actions AuditMode}
```

> [!TIP]
> Если вы хотите полностью проверять, как будут работать правила уменьшения поверхности атаки в вашей организации, вам потребуется использовать средство управления для развертывания этого параметра на устройствах в сети (s).

Для настройки и развертывания параметра можно также использовать поставщики услуг групповой политики, intune или службы управления мобильными устройствами (MDM). Дополнительные статьи в статье Правила уменьшения [поверхности](attack-surface-reduction.md) атаки.

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a>Просмотр событий уменьшения поверхности атаки в Windows viewer событий

Чтобы просмотреть заблокированные приложения, откройте viewer событий и фильтр для event ID 1121 в журнале Microsoft-Windows-Защитник Windows/Operational. В следующей таблице перечислены все события защиты сети.

Идентификатор события | Описание
-|-
 5007 | Событие при смене параметров
 1121 | Событие, когда правило уменьшения поверхности атаки загореется в режиме блокировки
 1122 | Событие, когда правило уменьшения поверхности атаки загореется в режиме аудита

## <a name="customize-attack-surface-reduction-rules"></a>Настройка правил сокращения направлений атак

Во время оценки может потребоваться настроить каждое правило по отдельности или исключить возможность оценки определенных файлов и процессов этой функцией.

Сведения [о настройке](customize-attack-surface-reduction.md) функции с помощью средств управления, включая политики групповой политики и CSP MDM, см. в этой ссылке.

## <a name="see-also"></a>См. также

* [Уменьшение поверхностей атаки с помощью правил уменьшения поверхности атаки](attack-surface-reduction.md)
* [Используйте режим аудита для оценки Защитник Windows](audit-windows-defender.md)
* [Сокращение направлений атак: вопросы и ответы](attack-surface-reduction.md)
