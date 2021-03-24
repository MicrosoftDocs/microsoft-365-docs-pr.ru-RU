---
title: Защита от угроз (Windows 10)
description: Microsoft Defender для конечной точки — это унифицированная платформа безопасности для конечных точек, которая обеспечивает превентивную защиту, обнаружение после взлома, автоматическое исследования и реагирование.
keywords: защита от угроз, расширенный уровень защиты от угроз Microsoft Defender, уменьшение поверхности атаки, защита следующего поколения, обнаружение конечных точек и реагирование, автоматическое расследование и реагирование, эксперты microsoft threat, Microsoft Secure Score для устройств, передовая охота, охота на киберугрозы, защита от веб-угроз
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 4206519d62feb82bbc297659e01b0cc3902b83dc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069207"
---
# <a name="threat-protection"></a>Защита от угроз
[Microsoft Defender для конечной точки](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection) — это унифицированная платформа безопасности для конечных точек, которая обеспечивает превентивную защиту, обнаружение после взлома, автоматическое исследования и реагирование. Defender for Endpoint защищает конечные точки от киберугроз, обнаруживает расширенные атаки и нарушения данных, автоматизирует инциденты с безопасностью и улучшает осанку безопасности.

> [!TIP]
> Позволяет пользователям легко получать доступ к облачным службам и приложениям на месте и включить современные возможности управления для всех устройств. Дополнительные сведения см. в [дополнительных сведениях о безопасности удаленных сотрудников.](https://docs.microsoft.com/enterprise-mobility-security/remote-work/) 

<center><h2>Microsoft Defender для конечной точки</center></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="threat and vulnerability icon"> <br><b>Управление & уязвимостей</b></center></a></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="attack surface reduction icon"> <br><b>Уменьшение поверхности атаки</b></center></a></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="next generation protection icon"><br> <b>Защита следующего поколения</b></a></center></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="endpoint detection and response icon"><br> <b>Обнаружение конечных точек и реагирование</b></a></center></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="automated investigation and remediation icon"><br> <b>Автоматическое расследование и исправление</b></a></center></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="microsoft threat experts icon"><br> <b>Эксперты по угрозам Майкрософт</b></a></center></td>
</tr>
<tr>
<td colspan="7">
<a href="#apis"><center><b>Централизованная конфигурация и администрирование, API</a></b></center></td>
</tr>
<tr>
<td colspan="7"><a href="#mtp"><center><b>Защитник Microsoft 365</a></center></b></td>
</tr>
</table>
<br>

<a name="tvm"></a>


>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4obJq]

**[Управление & уязвимостей](next-gen-threat-and-vuln-mgt.md)**<br>
Эта встроенная возможность использует подход к обнаружению, приоритетизации и исправлению уязвимостей конечной точки и неправильной оценки с учетом изменения рисков на основе игры.

- [Обзор управления & уязвимостей](next-gen-threat-and-vuln-mgt.md)
- [Начало работы](tvm-prerequisites.md)
- [Доступ к вашей позе безопасности](tvm-dashboard-insights.md)
- [Улучшение осанки безопасности и снижение риска](tvm-security-recommendation.md)
- [Понимание уязвимостей на устройствах](tvm-software-inventory.md)

<a name="asr"></a>

**[Сокращение направлений атак](overview-attack-surface-reduction.md)**<br>
Набор возможностей уменьшения поверхности атаки обеспечивает первую линию защиты в стеке. Обеспечивая правильное настройку параметров конфигурации и применяя методы смягчения последствий, этот набор возможностей позволяет противостоять атакам и эксплуатации.

- [Изолирование на основе оборудования](overview-hardware-based-isolation.md)
- [Элемент управления приложениями](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)
- [Управление устройствами](https://docs.microsoft.com/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)
- [Защита от эксплойтов](exploit-protection.md)
- [Защита сети,](network-protection.md) [веб-защита](web-protection-overview.md)
- [Управляемый доступ к папкам](controlled-folders.md)
- [Брандмауэр сети](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
- [Правила сокращения направлений атак](attack-surface-reduction.md)

<a name="ngp"></a>

**[Защита следующего поколения](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**<br>
Чтобы еще больше усилить периметр безопасности сети, Microsoft Defender для конечной точки использует защиту следующего поколения, предназначенную для улавливания всех типов возникающих угроз.

- [Мониторинг поведения](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)
- [Защита на основе облака](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-protection-features-microsoft-defender-antivirus)
- [Машинное обучение](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
- [Защита URL-адресов](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)
- [Автоматическая служба песочницы](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)

<a name="edr"></a>

**[Обнаружение и устранение угроз на конечных точках](overview-endpoint-detection-response.md)**<br>
Для обнаружения, расследования и реагирования на попытки вторжения и активных нарушений на месте работают возможности обнаружения конечных точек и реагирования на них. С помощью advanced hunting у вас есть средство охоты на угрозы на основе запросов, которое позволяет упреждающий поиск нарушений и создание настраиваемого обнаружения.

- [Alerts](alerts-queue.md)
- [Исторические конечные данные](investigate-machines.md#timeline)
- [Оркестровка ответов](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)
- [Коллекция судебной экспертизы](respond-machine-alerts.md#collect-investigation-package-from-devices)
- [Сведения об угрозах](threat-indicator-concepts.md)
- [Расширенные службы детонации и анализа](respond-file-alerts.md#deep-analysis)
- [Расширенная охота на угрозы](advanced-hunting-overview.md)
    - [Настраиваемое обнаружение](overview-custom-detections.md)

<a name="ai"></a>

**[Автоматическое исследование и защита](automated-investigations.md)**<br>
Помимо быстрого реагирования на расширенные атаки, Microsoft Defender for Endpoint предлагает возможности автоматического расследования и устранения, которые помогают уменьшить объем оповещений в минутах масштабирования.

- [Автоматическое исследование и защита](automated-investigations.md)
- [Просмотр сведений и результатов автоматических исследований](auto-investigation-action-center.md)
- [Просмотр и утверждение действий по исправлению](manage-auto-investigation.md)

<a name="mte"></a>

**[Microsoft Threat Experts](microsoft-threat-experts.md)**<br>
Новая служба управляемой охоты на угрозы в Microsoft Defender для Endpoint предоставляет активную охоту, приоритеты и дополнительные сведения и контекст. Эксперты Microsoft Threat также наделяет центры операций безопасности (SOCs) возможностями для быстрого и точного реагирования на угрозы.

- [Целевое уведомление об атаке](microsoft-threat-experts.md)
- [Эксперты по запросу](microsoft-threat-experts.md)
- [Настройка службы управляемого охотничьего ружья Microsoft 365 Defender](configure-microsoft-threat-experts.md)

<a name="apis"></a>

**[Централизованная конфигурация и администрирование, API](management-apis.md)**<br>
Интеграция Microsoft Defender для конечной точки в существующие процессы.
- [Адаптация](onboard-configure.md)
- [Интеграция API и SIEM](configure-siem.md)
- [Открытые API](apis-intro.md)
- [Управление доступом на основе ролей (RBAC)](rbac.md)
- [Отчеты и тенденции](threat-protection-reports.md)

<a name="integration"></a>
**[Интеграция с решениями Майкрософт](threat-protection-integration.md)** <br>
 Microsoft Defender для конечной точки напрямую интегрируется с различными решениями Майкрософт, в том числе:
- Intune
- Microsoft Defender для Office 365
- Microsoft Defender для удостоверений
- Azure Defender
- Skype для бизнеса
- Microsoft Cloud App Security

<a name="mtp"></a>
**[Защитник Microsoft 365](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)**<br>
 С помощью Microsoft 365 Defender, Microsoft Defender для endpoint и различных решений безопасности Майкрософт формируется единый пакет корпоративной защиты до и после нарушения, который интегрируется в конечную точку, удостоверение, электронную почту и приложения для обнаружения, предотвращения, расследования и автоматического реагирования на сложные атаки.
