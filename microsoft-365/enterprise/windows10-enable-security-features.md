---
title: Развертывание компонентов безопасности Windows 10 Корпоративная
description: Предоставляет высокоуровневое руководство по этапам, необходимым для развертывания функций системы безопасности Windows 10 Корпоративная на компьютерах в составе Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 корпоративный, документация по Microsoft 365, Windows 10 Корпоративная, безопасность
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
f1.keywords:
- NOCSH
ms.author: greglin
ms.openlocfilehash: 5407370933c2a99781adf4ca58d3fa905328ed04
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633007"
---
# <a name="step-5-deploy-windows-10-enterprise-security-features"></a>Шаг 5: развертывание компонентов безопасности Windows 10 Корпоративная

![Этап 3. Windows 10 Корпоративная](../media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Windows 10 предоставляет функции безопасности для защиты корпоративных пользователей, остановки киберугрозами и предотвращения потери данных. 

Дополнительные сведения об этих технологиях приведены в следующих статьях:

* [Защита удостоверений](https://docs.microsoft.com/windows/security/identity-protection/) — сведения о Windows Hello для бизнеса, Credential Guard и контроле доступа.
* [Защита от угроз](https://docs.microsoft.com/windows/threat-protection/) — Узнайте о Advanced Threat Protection в защитнике Майкрософт, единой платформе для защиты от вирусов, обнаружении нарушений, автоматическом расследовании и ответе.
* [Information Protection](https://docs.microsoft.com/windows/security/information-protection/) — сведения о BitLocker, Windows Information Protection и других способах защиты корпоративных данных с помощью Windows 10. 

На этом этапе показано, как можно развертывать, управлять, настраивать и устранять неполадки при использовании этих средств безопасности.

* [Антивирусная программа "Защитник Windows"](#windows-defender-antivirus)
* [Exploit Guard в Защитнике Windows](#windows-defender-exploit-guard)
* [Advanced Threat Protection в Microsoft Defender](#windows10-sec-atp)

<a name="windows10-sec-av"></a>
## <a name="windows-defender-antivirus"></a>Антивирусная программа "Защитник Windows"
Антивирусная программа "Защитник Windows" (AV) — это решение для защиты от вредоносных программ, встроенное в Windows 10. Он обеспечивает безопасность и защиту от вредоносных программ для настольных компьютеров, портативных компьютеров и серверов. Для получения дополнительных сведений о Защитнике Windows (AV), минимальных требованиях и способах управления этой функцией обратитесь к [антивирусной программе "Защитник Windows" в Windows 10 и Windows Server 2016](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10).

Если вы не используете Windows Defender AV в качестве основного антивирусного клиента, или если вы также используете Microsoft Defender ATP, необходимо учитывать некоторые моменты. Чтобы узнать больше, ознакомьтесь со статьей [Совместимость с защитником Windows AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-compatibility).

### <a name="deployment-and-management"></a>Развертывание и управление
Для развертывания и управления Защитником Windows AV следуйте указаниям ниже.

* [Развертывание, управление и составление отчетов о Защитнике Windows (AV)](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [Справочные разделы, посвященные средствам управления и настройки](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

### <a name="configuration"></a>Конфигурация
Пользователи могут настраивать ряд функций. Более подробную информацию можно найти в следующих ресурсах:

* [Настройка антивирусной функции защитника Windows](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)
* [Справочные разделы, посвященные средствам управления и настройки](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

Чтобы получить сведения о параметрах конфигурации, обратитесь к этому списку всех параметров (определенных в соответствии с их конфигурацией групповой политики): [Использование параметров групповой политики для настройки и управления Защитником Windows AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/use-group-policy-windows-defender-antivirus)

Вы можете использовать [руководство по проверке защиты от вирусов защитника Windows](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/evaluate-windows-defender-antivirus) для оценки уровня защиты и воздействия защитника Windows в сети. Это также может быть полезно при создании начальной конфигурации или в кратком руководстве и регулярно обновляется для предоставления наиболее полезной рекомендации по настройке и включению функций для обеспечения максимальной защиты.

### <a name="reporting"></a>Reporting
Вы можете получить отчеты с помощью средства настройки, например Microsoft Endpoint Configuration Manager или Microsoft Intune. Вы также можете получить отчеты о соответствии обновления (OMS) или с помощью журналов событий Windows в SIEM. Если у вас есть лицензия на пакет ATP для защитника Microsoft, вы также можете получить отчеты об обнаружении Windows Defender AV и выполнить базовое исправление. Более подробную информацию можно найти в следующих ресурсах:
* [Развертывание, управление и составление отчетов о Защитнике Windows (AV)](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [Отчет о защите от вирусов защитника Windows](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/report-monitor-windows-defender-antivirus)
* [Общие сведения о портале ATP для защитника Майкрософт](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>Устранение неполадок
Для получения сведений о базовом устранении ошибок и кодов событий просмотрите [журналы событий и коды ошибок, чтобы устранить неполадки, связанные с защитником Windows AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus).

Вы также можете отправлять проблемы (например, ложные срабатывания) с помощью системы отправки системы безопасности для защитника Windows. Сведения о том, как [отправляйте вопросы в корпорацию Майкрософт](https://www.microsoft.com/wdsi/filesubmission).

<a name="windows10-sec-eg"></a>
## <a name="windows-defender-exploit-guard"></a>Exploit Guard в Защитнике Windows
Система защиты от использования защитника Windows — это новый набор возможностей предотвращения вторжения на хост-узел для Windows 10. Дополнительные сведения о защите от эксплойтов Windows Defender, минимальных требованиях и способах управления этой функцией можно найти в разделе [Windows Defender эксплойт](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard).

### <a name="deployment-management-and-configuration"></a>Развертывание, управление и настройка
Для развертывания, управления и настройки средства защиты от использования защитника Windows следуйте указаниям ниже.
* [Защита от эксплойтов](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/exploit-protection-exploit-guard)
* [Защита от уязвимой зоны](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard?ocid=cx-docs-msa4053440)
* [Защита сети](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/network-protection-exploit-guard)
* [Контролируемый доступ к папкам](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard)

Вы можете использовать серию статей, посвященных оценке уровня защиты и влиянии системы защиты от использования защитника Windows в вашей сети. Это также может пригодиться при создании начальной конфигурации или в виде краткого руководства по началу, а также регулярно обновлять темы и рекомендации по настройке и включению функций, обеспечивающих максимальную защиту. Для получения дополнительных сведений [оцените защиту от использования защитника Windows](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/evaluate-windows-defender-exploit-guard).

### <a name="reporting"></a>Reporting
Вы можете получить отчеты с помощью средства настройки, например Configuration Manager или Intune. Кроме того, вы можете получить отчеты, используя журналы событий Windows в SIEM. Если у вас есть лицензия на пакет ATP для защитника Microsoft, вы также можете получить отчеты об обнаружении Windows Defender AV и выполнить базовое исправление. Более подробную информацию можно найти в следующих ресурсах:
* [Просмотр событий эксплойта Windows Defender Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/event-views-exploit-guard)
* [Общие сведения о портале ATP для защитника Майкрософт](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>Устранение неполадок
Вы можете выполнить основные действия по устранению неполадок или дополнительно предоставить корпорации Майкрософт файлы CAB и отправить проблемы (например, ложные срабатывания) с помощью системы отправки системы безопасности для защитника Windows. Сведения о том, как [отправляйте вопросы в корпорацию Майкрософт](https://www.microsoft.com/wdsi/filesubmission).


<a name="windows10-sec-atp"></a>
## <a name="microsoft-defender-advanced-threat-protection"></a>Advanced Threat Protection в Microsoft Defender
Защитник Майкрософт, доступный только в плане Microsoft 365, — это служба безопасности, позволяющая корпоративным клиентам обнаруживать, изучать и отвечать на дополнительные угрозы в своих сетях. Для получения дополнительных сведений о Microsoft Defender ATP, минимальных требованиях и способах управления этой функцией обратитесь к разделу:

* [ATP в Microsoft Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)
* [Минимальные требования](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/minimum-requirements-windows-defender-advanced-threat-protection)

### <a name="deployment-management-and-configuration"></a>Развертывание, управление и настройка
Для развертывания пакета ATP для защитника Microsoft необходимо убедиться, что у вас есть нужная лицензия Windows. Убедившись, что у вас есть правильная лицензия, вам потребуется выбрать географическое расположение для хранения данных. После этого вы сможете начать приподключение к службе конечных точек.

Более подробную информацию об этих действиях можно узнать в следующих разделах: 

* [Проверка подготовки лицензирования и завершения настройки](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/licensing-windows-defender-advanced-threat-protection)
* [Хранение и конфиденциальность данных](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/data-storage-privacy-windows-defender-advanced-threat-protection)
* [Встроенные конечные точки и доступ для установки](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/onboard-configure-windows-defender-advanced-threat-protection)

### <a name="detect-investigate-respond"></a>Поиск, исследование, ответ
После успешной адаптации конечных точек к службе вы можете начать исследование оповещений с различных панелей мониторинга. После того как вы изучили оповещения, вы можете принять действия по отклику на оповещения. 

Дополнительные сведения о том, как это сделать, см.
* [Общие сведения о портале ATP для защитника Майкрософт](https://go.microsoft.com/fwlink/?linkid=861596)
* [Использование портала Microsoft Defender ATP](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-windows-defender-advanced-threat-protection)
* [Выполнение действий ответа](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/response-actions-windows-defender-advanced-threat-protection)

### <a name="integrate-with-other-products-and-tools"></a>Интеграция с другими продуктами и средствами
Защитник Microsoft Defender интегрирует и поддерживает различные другие продукты и средства для расширения возможностей обеспечения безопасности. 

Дополнительные сведения о средствах и других продуктах можно найти в следующих статьях:
* [Средства SIEM](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/configure-siem-windows-defender-advanced-threat-protection)
* [Создание настраиваемых оповещений](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-custom-ti-windows-defender-advanced-threat-protection)
* [Использование API](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/exposed-apis-windows-defender-advanced-threat-protection)
* [Создание отчетов Power BI](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/powerbi-reports-windows-defender-advanced-threat-protection)

### <a name="troubleshooting"></a>Устранение неполадок
Во время входящей миграции или при использовании продукта могут возникнуть проблемы. Более подробную информацию о том, как решать проблемы, можно найти в следующих статьях:
* [Устранение проблем с входящей миграции](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-onboarding-windows-defender-advanced-threat-protection)
* [Устранение неполадок в защитнике Microsoft](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-windows-defender-advanced-threat-protection)

## <a name="next-step"></a>Следующий шаг

[Критерии выхода инфраструктуры Windows 10 Корпоративная](windows10-exit-criteria.md)
