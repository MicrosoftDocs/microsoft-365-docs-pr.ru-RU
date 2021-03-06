---
title: Microsoft Defender для конечной точки
description: Microsoft Defender для конечной точки — это платформа безопасности конечной точки предприятия, которая помогает защититься от сложных постоянных угроз.
keywords: введение в Microsoft Defender для конечной точки, введение в Microsoft Defender для конечной точки, кибербезопасность, расширенные сохраняемая угроза, безопасность предприятия, датчик поведения машины, облачная безопасность, аналитика, аналитика угроз, уменьшение поверхности атак, защита от атак следующего поколения, автоматическое расследование и исправление, эксперты по угрозам Майкрософт, оценка безопасности, расширенный поиск, Microsoft 365 Defender, охота на киберугрозы
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 23a9b99a71d700bdeddb3398c592eeb778ceef23
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879268"
---
# <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender для конечной точки

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> Дополнительные сведения о возможностях Windows 10 Корпоративная Edition см. в Windows 10 Корпоративная [edition.](https://www.microsoft.com/WindowsForBusiness/buy)

Microsoft Defender for Endpoint — это корпоративная платформа безопасности конечной точки, предназначенная для предотвращения, обнаружения, обнаружения, обнаружения и реагирования на расширенные угрозы.
<p></p>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wDob]

Defender for Endpoint использует следующее сочетание технологий, встроенных в Windows 10 и надежную облачную службу Майкрософт:

-   Датчики поведения конечной точки. Встроенные в Windows 10, эти датчики собирают и обрабатывает поведенческие сигналы из операционной системы и отправляют эти данные датчика в частный изолированный облачный экземпляр Microsoft Defender для Endpoint.


-   Аналитика облачной **безопасности:** использование больших данных, обучения устройствам и уникальной оптики Майкрософт в экосистеме Windows, корпоративных облачных продуктов (таких как Office 365) и сетевых активов, поведенческие сигналы преобразуются в аналитические сведения, обнаружения и рекомендуемые ответы на расширенные угрозы.

-   Сведения об угрозах. Созданные охотниками Майкрософт, группами безопасности и дополненные сведениями об угрозах, предоставляемыми партнерами, сведения об угрозах позволяют Defender for Endpoint определять средства, методы и процедуры злоумышленника, а также создавать оповещения при их наблюдении в собранных данных датчиков.

<center><h2>Microsoft Defender для конечной точки</center></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="Threat & Vulnerability Management"> <br><b>Управление & уязвимостей</b></center></a></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="Attack surface reduction"><br><b>Уменьшение поверхности атаки</b></center></a></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="Next-generation protection"><br> <b>Защита следующего поколения</b></a></center></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="Endpoint detection and response"><br> <b>Обнаружение конечных точек и реагирование</b></a></center></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="Automated investigation and remediation"><br> <b>Автоматическое расследование и исправление</b></a></center></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="Microsoft Threat Experts"><br> <b>эксперты Майкрософт по угрозам</b></a></center></td>
</tr>
<tr>
<td colspan="7">
<a href="#apis"><center><b>Централизованная конфигурация и администрирование, API</a></b></center></td>
</tr>
<tr>
<td colspan="7"><a href="#mtp"><center><b>Microsoft 365 Defender</a></center></b></td>
</tr>
</table>
<br>

<p></p>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vnC4?rel=0] 

> [!TIP]
> - Узнайте о последних улучшениях в Defender для конечной точки: что нового в [Microsoft Defender для конечной точки](whats-new-in-microsoft-defender-atp.md).
> - В недавней оценке MITRE Microsoft Defender for Endpoint продемонстрировала передовые в отрасли возможности оптики и обнаружения. Read: [Insights from the MITRE ATT&CK-based assessment](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).

<a name="tvm"></a>

**[Управление & уязвимостей](next-gen-threat-and-vuln-mgt.md)**<br>
Эта встроенная возможность использует подход к обнаружению, приоритетизации и исправлению уязвимостей конечной точки и неправильной оценки с учетом изменения рисков на основе игры. 

<a name="asr"></a>

**[Сокращение направлений атак](overview-attack-surface-reduction.md)**<br>
Набор возможностей уменьшения поверхности атаки обеспечивает первую линию защиты в стеке. Обеспечивая правильное настройку параметров конфигурации и применяя методы смягчения последствий, возможности сопротивляются атакам и эксплуатации. Этот набор возможностей также [](network-protection.md) включает защиту сети и [веб-защиту,](web-protection-overview.md)которые регулируют доступ к вредоносным IP-адресам, доменам и URL-адресам. 

<a name="ngp"></a>

**[Защита нового поколения](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**<br>
Чтобы еще больше усилить периметр безопасности сети, Microsoft Defender для конечной точки использует защиту следующего поколения, предназначенную для улавливания всех типов возникающих угроз.

<a name="edr"></a>

**[Обнаружение и устранение угроз на конечных точках](overview-endpoint-detection-response.md)**<br>
Для обнаружения, расследования и реагирования на расширенные угрозы, которые могли оказаться за первыми двумя столпами безопасности, вложены возможности обнаружения конечных точек и их реагирования. [Расширенный способ охоты](advanced-hunting-overview.md) предоставляет средство для поиска угроз на основе запросов, которое позволяет упреждающий поиск нарушений и создание настраиваемого обнаружения.

<a name="ai"></a>

**[Автоматическое расследование и исправление](automated-investigations.md)**<br>
В сочетании с возможностью быстрого реагирования на расширенные атаки Microsoft Defender for Endpoint предлагает возможности автоматического расследования и устранения, которые помогают уменьшить объем оповещений в минутах масштабирования. 

<a name="ss"></a>

**[Оценка безопасности (Майкрософт) для устройств](tvm-microsoft-secure-score-devices.md)**<br>

Defender for Endpoint включает microsoft Secure Score for Devices, чтобы помочь вам динамически оценить состояние безопасности корпоративной сети, определить незащищенные системы и принять рекомендуемые действия для повышения общей безопасности организации.

<a name="mte"></a>

**[Эксперты Майкрософт по угрозам](microsoft-threat-experts.md)**<br>
Новая служба управляемой охоты на угрозы Microsoft Defender для конечной точки обеспечивает активную охоту, приоритеты и дополнительные сведения, которые расширяют возможности центров операций безопасности (SOCs) для быстрого и точного реагирования на угрозы.

>[!IMPORTANT]
>Defender for Endpoint customers need to apply for the эксперты Майкрософт по угрозам managed threat hunting service to get proactive Targeted Attack Notifications and to collaborate with experts on demand. Эксперты по запросу — это служба надстройки. Целевые уведомления о атаке всегда включаются после того, как вы были приняты в эксперты Майкрософт по угрозам службу управляемой охоты на угрозы.<p>
><p>Если вы еще не зарегистрированы и хотите испытать <b></b> его преимущества, перейдите Параметры > <b>общие</b> > <b></b> расширенные эксперты Майкрософт по угрозам > <b>применить.</b> После его 30-дневного использования вы получите преимущества целевых уведомлений об атаке и запустите 90-дневную пробную работу экспертов по запросу. Свяжитесь со своим представителем Майкрософт, чтобы получить полный список экспертов по подписке На запрос.

<a name="apis"></a>

**[Централизованная конфигурация и администрирование, API](management-apis.md)**<br>
Интеграция Microsoft Defender для конечной точки в существующие процессы.

<a name="mtp"></a>

**[Интеграция с решениями Майкрософт](threat-protection-integration.md)** <br>
Defender for Endpoint напрямую интегрируется с различными решениями Майкрософт, в том числе:
- Azure Defender
- Azure Sentinel
- Intune
- Microsoft Cloud App Security
- Microsoft Defender для удостоверений
- Microsoft Defender для Office
- Skype для бизнеса

**[Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-threat-protection)**<br>
С Microsoft 365 Defender, Defender for Endpoint и различными решениями безопасности Майкрософт образуют единый пакет защиты предприятия до и после нарушения, который интегрируется в конечные точки, удостоверения, электронную почту и приложения для обнаружения, предотвращения, расследования и автоматического реагирования на сложные атаки.


## <a name="related-topic"></a>Связанная тема
[Microsoft Defender для конечной точки помогает обнаруживать сложные угрозы](https://www.microsoft.com/itshowcase/microsoft-defender-atps-antivirus-capabilities-boost-malware-protection)
