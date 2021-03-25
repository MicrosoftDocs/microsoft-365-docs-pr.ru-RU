---
title: Использование сетевой защиты для предотвращения подключения к плохим сайтам
description: Защита сети путем предотвращения доступа пользователей к известным вредоносным и подозрительным сетевым адресам
keywords: Защита сети, эксплойтов, вредоносный веб-сайт, IP, домен, домены
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
ms.custom: asr
ms.technology: mde
ms.date: 03/08/2021
ms.topic: how-to
ms.openlocfilehash: be98bf810d00b6e39ba9d2674604a9fd2128a8cc
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198661"
---
# <a name="protect-your-network"></a>Защита сети

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Защита сети помогает уменьшить поверхность атаки устройств от событий, происходящих в Интернете. Это не позволяет сотрудникам использовать любое приложение для доступа к опасным доменам, в которые могут быть организованы фишинговые атаки, эксплойты и другой вредоносный контент в Интернете. Защита от сети расширяет область [SmartScreen Microsoft Defender,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) чтобы заблокировать весь исходящий трафик HTTP(s), который пытается подключиться к источникам с низкой репутацией (на основе домена или имени хост-сайта).

Защита сети поддерживается в Windows, начиная с Windows 10 версии 1709. 

Дополнительные сведения о том, как включить защиту сети, см. в дополнительных [сведениях о том, как включить защиту сети.](enable-network-protection.md) Используйте групповой политики, PowerShell или MDM CSPs для обеспечения и управления сетевой защитой в сети.

> [!TIP]
> Узнайте, как работает защита сети, demo.wd.microsoft.com на [сайте тестового поля ATP](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) Защитника Майкрософт.

Защита сети лучше всего работает с [Microsoft Defender для конечной](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)точки , которая предоставляет подробные отчеты о событиях и блоках защиты от эксплуатации в рамках сценариев расследования [оповещения.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)

Когда защита сети блокирует подключение, из Центра действий отображается уведомление. Группа операций безопасности может [настроить уведомление](customize-attack-surface-reduction.md#customize-the-notification) с помощью сведений и контактных данных организации. Кроме того, отдельные правила уменьшения поверхности атаки можно включить и настроить в соответствии с определенными методами мониторинга.

Вы также можете использовать [режим аудита](audit-windows-defender.md) для оценки влияния сетевой защиты на организацию, если она включена.

## <a name="requirements"></a>Требования

Защита сети требует защиты Windows 10 Pro или Enterprise и антивируса Microsoft Defender в режиме реального времени.

| Версия Windows | Антивирус Microsoft Defender |
|:---|:---|
| Windows 10 версии 1709 или более поздней версии <p>Windows Server 1803 или более поздней версии | [Антивирус Microsoft Defender в режиме реального времени и](https://docs.microsoft.com/windows/security/threat-protection/configure-real-time-protection-microsoft-defender-antivirus.md) [облачная](https://docs.microsoft.com/windows/security/threat-protection/enable-cloud-protection-microsoft-defender-antivirus.md) защита должны быть включены |

После включения служб может потребоваться настроить сеть или брандмауэр, чтобы разрешить подключения между службами и устройствами (также именуемые конечными точками).  

- .smartscreen.microsoft.com
- .smartscreen-prod.microsoft.com

## <a name="review-network-protection-events-in-the-microsoft-defender-for-endpoint-security-center"></a>Просмотр событий защиты сети в Центре безопасности конечных точек Microsoft Defender для конечных точек

Microsoft Defender for Endpoint предоставляет подробные отчеты о событиях и блоках в рамках сценариев расследования [оповещений.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)

Вы можете запрашивать данные Microsoft Defender для конечных точек с помощью [расширенных методов охоты.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-windows-defender-advanced-threat-protection) Если вы используете [](audit-windows-defender.md)режим аудита, вы можете использовать расширенный режим охоты, чтобы узнать, как параметры сетевой защиты влияют на среду, если они включены.

Вот пример запроса

```kusto
DeviceEvents
| where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a>Просмотр событий защиты сети в Windows Event Viewer

Вы можете просмотреть журнал событий Windows, чтобы просмотреть события, созданные при блоке сетевой защиты (или аудите) доступа к вредоносному IP или домену:

1. [Скопируйте XML напрямую.](event-views.md)

2. Нажмите кнопку **ОК**.

Эта процедура создает настраиваемую точку зрения, которая фильтрует только следующие события, связанные с защитой сети:

| Идентификатор события | Описание |
|:---|:---|
| 5007 | Событие при смене параметров |
| 1125 | Событие, когда защита сети загорелась в режиме аудита |
| 1126 | Событие, когда защита сети загорелась в режиме блокировки |

## <a name="related-articles"></a>Статьи по теме

- [Оценка защиты](evaluate-network-protection.md) сети | Создай быстрый сценарий, в который показано, как работает функция и какие события обычно создаются.

- [Включить защиту](enable-network-protection.md) сети | Используйте групповой политики, PowerShell или MDM CSPs для обеспечения и управления сетевой защитой в сети.
