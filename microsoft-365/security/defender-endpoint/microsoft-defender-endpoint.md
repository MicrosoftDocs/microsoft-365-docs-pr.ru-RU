---
title: Microsoft Defender для конечной точки
description: Microsoft Defender для конечной точки — это платформа безопасности конечной точки предприятия, которая помогает защититься от сложных постоянных угроз.
keywords: введение в Microsoft Defender для конечной точки, введение в Microsoft Defender Advanced Threat Protection, введение в Microsoft Defender ATP, кибербезопасность, расширенные постоянные угрозы, безопасность предприятия, датчик поведения машины, облачная безопасность, аналитика, разведка угроз, уменьшение поверхности атак, защита от атак следующего поколения, автоматическое расследование и исправление, эксперты microsoft threat, безопасный результат, расширенный уровень охоты, защита от угроз Майкрософт, охота на киберугрозы
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
ms.openlocfilehash: 8c5d02a4d76ae7e031ad9f3af0db282cc4cb45ed
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187319"
---
# <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender для конечной точки

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> Дополнительные сведения о возможностях и функциях Windows 10 Enterprise Edition см. в [выпуске Windows 10 Enterprise.](https://www.microsoft.com/WindowsForBusiness/buy)

Microsoft Defender for Endpoint — это корпоративная платформа безопасности конечной точки, предназначенная для предотвращения, обнаружения, обнаружения, обнаружения и реагирования на расширенные угрозы.
<p></p>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wDob]

Defender for Endpoint использует следующую комбинацию технологий, встроенных в Windows 10 и надежную облачную службу Майкрософт:

-   Датчики поведения конечной точки. Встроенные в Windows 10, эти датчики собирают и обрабатывает поведенческие сигналы из операционной системы и отправляют эти данные датчика в частный изолированный облачный экземпляр Microsoft Defender для endpoint.


-   Аналитика облачной **безопасности:** использование больших данных, обучения устройствам и уникальной оптики Microsoft в экосистеме Windows, корпоративных облачных продуктов (например, Office 365) и сетевых активов, поведенческие сигналы преобразуются в аналитические сведения, обнаружения и рекомендуемые ответы на расширенные угрозы.

-   Сведения об угрозах. Созданные охотниками Майкрософт, группами безопасности и дополненные сведениями об угрозах, предоставляемыми партнерами, сведения об угрозах позволяют Defender for Endpoint определять средства, методы и процедуры злоумышленника, а также создавать оповещения при их наблюдении в собранных данных датчиков.

<center><h2>Microsoft Defender для конечной точки</center></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="Threat & Vulnerability Management"> <br><b>Управление & уязвимостей</b></center></a></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="Attack surface reduction"><br><b>Уменьшение поверхности атаки</b></center></a></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="Next-generation protection"><br> <b>Защита следующего поколения</b></a></center></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="Endpoint detection and response"><br> <b>Обнаружение конечных точек и реагирование</b></a></center></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="Automated investigation and remediation"><br> <b>Автоматическое расследование и исправление</b></a></center></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="Microsoft Threat Experts"><br> <b>Эксперты по угрозам Майкрософт</b></a></center></td>
</tr>
<tr>
<td colspan="7">
<a href="#apis"><center><b>Централизованная конфигурация и администрирование, API</a></b></center></td>
</tr>
<tr>
<td colspan="7"><a href="#mtp"><center><b>Защита от угроз Майкрософт</a></center></b></td>
</tr>
</table>
<br>

<p></p>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vnC4?rel=0] 

> [!TIP]
> - Узнайте о последних улучшениях в Defender для конечной точки: что нового в [Microsoft Defender для конечной точки](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).
> - В недавней оценке MITRE Microsoft Defender for Endpoint продемонстрировала передовые в отрасли возможности оптики и обнаружения. Read: [Insights from the MITRE ATT&CK-based assessment](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).

<a name="tvm"></a>

**[Управление & уязвимостей](next-gen-threat-and-vuln-mgt.md)**<br>
Эта встроенная возможность использует подход к обнаружению, приоритетизации и исправлению уязвимостей конечной точки и неправильной оценки с учетом изменения рисков на основе игры. 

<a name="asr"></a>

**[Сокращение направлений атак](overview-attack-surface-reduction.md)**<br>
Набор возможностей уменьшения поверхности атаки обеспечивает первую линию защиты в стеке. Обеспечивая правильное настройку параметров конфигурации и применяя методы смягчения последствий, возможности сопротивляются атакам и эксплуатации. Этот набор возможностей также [](network-protection.md) включает защиту сети и [веб-защиту,](web-protection-overview.md)которые регулируют доступ к вредоносным IP-адресам, доменам и URL-адресам. 

<a name="ngp"></a>

**[Защита следующего поколения](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**<br>
Чтобы еще больше усилить периметр безопасности сети, Microsoft Defender для конечной точки использует защиту следующего поколения, предназначенную для улавливания всех типов возникающих угроз.

<a name="edr"></a>

**[Обнаружение и устранение угроз на конечных точках](overview-endpoint-detection-response.md)**<br>
Для обнаружения, расследования и реагирования на расширенные угрозы, которые могли оказаться за первыми двумя столпами безопасности, вложены возможности обнаружения конечных точек и их реагирования. [Расширенный способ охоты](advanced-hunting-overview.md) предоставляет средство для поиска угроз на основе запросов, которое позволяет упреждающий поиск нарушений и создание настраиваемого обнаружения.

<a name="ai"></a>

**[Автоматическое исследование и защита](automated-investigations.md)**<br>
В сочетании с возможностью быстрого реагирования на расширенные атаки Microsoft Defender for Endpoint предлагает возможности автоматического расследования и устранения, которые помогают уменьшить объем оповещений в минутах масштабирования. 

<a name="ss"></a>

**[Microsoft Secure Score для устройств](tvm-microsoft-secure-score-devices.md)**<br>

Defender for Endpoint включает microsoft Secure Score for Devices, чтобы помочь вам динамически оценить состояние безопасности корпоративной сети, определить незащищенные системы и принять рекомендуемые действия для повышения общей безопасности организации.

<a name="mte"></a>

**[Microsoft Threat Experts](microsoft-threat-experts.md)**<br>
Новая служба управляемой охоты на угрозы Microsoft Defender для конечной точки обеспечивает активную охоту, приоритеты и дополнительные сведения, которые расширяют возможности центров операций безопасности (SOCs) для быстрого и точного реагирования на угрозы.

>[!IMPORTANT]
>Защитник для клиентов конечных точек должен обратиться в службу управляемой охоты на угрозы microsoft Threat Experts для получения активных уведомлений о целевых атаках и для совместной работы с экспертами по запросу. Эксперты по запросу — это служба надстройки. Целевые уведомления о атаке всегда включаются после того, как вы были приняты в службу управляемых угроз Microsoft Threat Experts.<p>
><p>Если вы еще не зарегистрированы и хотите испытать его преимущества, перейдите в <b>параметры</b> > <b>Общие</b> > <b></b> расширенные функции > <b>Microsoft Threat Experts</b> для применения. После его 30-дневного использования вы получите преимущества целевых уведомлений об атаке и запустите 90-дневную пробную работу экспертов по запросу. Свяжитесь со своим представителем Майкрософт, чтобы получить полный список экспертов по подписке На запрос.

<a name="apis"></a>

**[Централизованная конфигурация и администрирование, API](management-apis.md)**<br>
Интеграция Microsoft Defender для конечной точки в существующие процессы.

<a name="mtp"></a>

**[Интеграция с решениями Майкрософт](threat-protection-integration.md)** <br>
Defender for Endpoint напрямую интегрируется с различными решениями Майкрософт, в том числе:
- Центр безопасности Azure
- Azure Sentinel
- Intune
- Microsoft Cloud App Security
- Microsoft Defender для удостоверений
- Microsoft Defender для Office
- Skype для бизнеса

**[Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)**<br>
С помощью Microsoft 365 Defender, Defender for Endpoint и различных решений безопасности Майкрософт формируется единый пакет корпоративной защиты до и после нарушения, который интегрируется в конечную точку, удостоверение, электронную почту и приложения для обнаружения, предотвращения, расследования и автоматического реагирования на сложные атаки.


## <a name="related-topic"></a>Связанная тема
[Microsoft Defender для конечной точки помогает обнаруживать сложные угрозы](https://www.microsoft.com/itshowcase/microsoft-defender-atps-antivirus-capabilities-boost-malware-protection)
