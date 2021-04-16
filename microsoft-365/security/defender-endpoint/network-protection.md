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
ms.topic: how-to
ms.openlocfilehash: a22cab9185b2ece2e8e30c00ea747cca823f4920
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861159"
---
# <a name="protect-your-network"></a>Защита сети

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Защита сети помогает уменьшить поверхность атаки устройств от событий, происходящих в Интернете. Это не позволяет сотрудникам использовать любое приложение для доступа к опасным доменам, в которые могут быть организованы фишинговые атаки, эксплойты и другой вредоносный контент в Интернете. Защита от сети расширяет область [SmartScreen Microsoft Defender,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) чтобы заблокировать весь исходящий трафик HTTP(s), который пытается подключиться к источникам с низкой репутацией (на основе домена или имени хост-сайта).

Защита сети поддерживается в Windows, начиная с Windows 10 версии 1709. Защита сети еще не поддерживается в других операционных системах, но веб-защита поддерживается с помощью нового Microsoft Edge на основе Chromium. Дополнительные информации см. в [веб-защите.](web-protection-overview.md)

Защита сети расширяет защиту в [веб-защите](web-protection-overview.md) до уровня операционной системы. Он предоставляет функции веб-защиты в Edge для других поддерживаемых браузеров и не браузерных приложений. Кроме того, защита сети обеспечивает видимость и блокировку индикаторов компрометации (IOCs) при их обнаружении и реагировании на [конечные точки.](overview-endpoint-detection-response.md) Например, защита сети работает с [настраиваемой индикаторами.](manage-indicators.md)

Дополнительные сведения о том, как включить защиту сети, см. в дополнительных [сведениях о том, как включить защиту сети.](enable-network-protection.md) Используйте групповой политики, PowerShell или MDM CSPs для обеспечения и управления сетевой защитой в сети.

> [!TIP]
> Узнайте, как работает защита сети, на demo.wd.microsoft.com сайте microsoft Defender [for](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) Endpoint.

Защита сети лучше всего работает с [Microsoft Defender для конечной](microsoft-defender-endpoint.md)точки , которая предоставляет подробные отчеты о событиях и блоках защиты от эксплуатации в рамках сценариев расследования [оповещения.](investigate-alerts.md)

Когда защита сети блокирует подключение, из Центра действий отображается уведомление. Группа операций безопасности может [настроить уведомление](customize-attack-surface-reduction.md#customize-the-notification) с помощью сведений и контактных данных организации. Кроме того, отдельные правила уменьшения поверхности атаки можно включить и настроить в соответствии с определенными методами мониторинга.

Вы также можете использовать [режим аудита](audit-windows-defender.md) для оценки влияния сетевой защиты на организацию, если она включена.

## <a name="requirements"></a>Требования

Защита сети требует защиты Windows 10 Pro или Enterprise и антивируса Microsoft Defender в режиме реального времени.

| Версия Windows | Антивирусная программа в Microsoft Defender |
|:---|:---|
| Windows 10 версии 1709 или более поздней версии <p>Windows Server 1803 или более поздней версии | [Антивирус Microsoft Defender в режиме реального времени и](configure-real-time-protection-microsoft-defender-antivirus.md) [облачная](enable-cloud-protection-microsoft-defender-antivirus.md) защита должны быть включены |

После включения служб может потребоваться настроить сеть или брандмауэр, чтобы разрешить подключения между службами и устройствами (также именуемые конечными точками).  

- `.smartscreen.microsoft.com`
- `.smartscreen-prod.microsoft.com`

## <a name="review-network-protection-events-in-the-microsoft-defender-for-endpoint-security-center"></a>Просмотр событий защиты сети в Центре безопасности конечных точек Microsoft Defender для конечных точек

Microsoft Defender for Endpoint предоставляет подробные отчеты о событиях и блоках в рамках сценариев расследования [оповещений.](investigate-alerts.md)

Вы можете запрашивать данные Microsoft Defender для конечных точек с помощью [расширенных методов охоты.](advanced-hunting-overview.md) Если вы используете [](audit-windows-defender.md)режим аудита, вы можете использовать расширенный режим охоты, чтобы узнать, как параметры сетевой защиты влияют на среду, если они включены.

Вот пример запроса

```kusto
DeviceEvents
| where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a>Просмотр событий защиты сети в Windows Event Viewer

Вы можете просмотреть журнал событий Windows, чтобы просмотреть события, созданные при блоке сетевой защиты (или аудите) доступа к вредоносному IP или домену:

1. [Скопируйте XML напрямую.](event-views.md)

2. Нажмите **ОК**.

Эта процедура создает настраиваемую точку зрения, которая фильтрует только следующие события, связанные с защитой сети:

| Идентификатор события | Описание |
|:---|:---|
| 5007 | Событие при смене параметров |
| 1125 | Событие, когда защита сети загорелась в режиме аудита |
| 1126 | Событие, когда защита сети загорелась в режиме блокировки |

## <a name="considerations-for-windows-virtual-desktop-running-windows-10-enterprise-multi-session"></a>Соображения для виртуального рабочего стола Windows под управлением Windows 10 Корпоративная мульти-сессия

Учитывая многоцелевую природу Windows 10 Enterprise, следует помнить о следующих моментах:

1. Защита от сети — это функция для всего устройства и не может быть ориентирована на определенные сеансы пользователей.

2. Политики фильтрации веб-контента также являются широкими устройствами.

3. Если необходимо различать группы пользователей, рассмотрите возможность создания отдельных пулов и назначений для виртуальных настольных компьютеров Windows.

4. Проверьте защиту сети в режиме аудита, чтобы оценить ее поведение перед развертыванием. 

5. Рассмотрите возможность повторного развертывания, если у вас большое количество пользователей или большое количество сеансов с несколькими пользователями.

### <a name="alternative-option-for-network-protection"></a>Альтернативный вариант защиты сети

Для Windows 10 Enterprise Multi-Session 1909 и up, используемой в Windows Virtual Desktop в Azure, можно включить защиту сети для Microsoft Edge с помощью следующего метода:

1. [Включите защиту сети](enable-network-protection.md) и следуйте инструкциям, чтобы применить политику.

2. Выполните следующую команду PowerShell: `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`

## <a name="network-protection-troubleshooting"></a>Устранение неполадок в сетевой защите

Из-за среды, в которой выполняется защита сети, Microsoft может не обнаруживать параметры прокси-сервера операционной системы. В некоторых случаях клиенты сетевой защиты не могут добраться до облачной службы. Чтобы устранить проблему подключения, клиенты с лицензиями E5 должны настроить один из следующих ключей реестра Defender:

```console
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f

```

## <a name="related-articles"></a>Статьи по теме

- [Оценка защиты](evaluate-network-protection.md) сети | Создай быстрый сценарий, в который показано, как работает функция и какие события обычно создаются.

- [Включить защиту](enable-network-protection.md) сети | Используйте групповой политики, PowerShell или MDM CSPs для обеспечения и управления сетевой защитой в сети.
