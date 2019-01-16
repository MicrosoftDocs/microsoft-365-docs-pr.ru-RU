---
title: Развертывание компонентов безопасности Windows 10 Enterprise
description: Высокоуровневая рекомендации на действия, необходимые для развертывания корпоративной 10 Windows на компьютерах в составе Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365 документации Windows 10 Enterprise безопасности
author: greg-lindsay
localization_priority: Normal
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
ms.author: greglin
ms.openlocfilehash: d051f9e56d8e9986fbe0975c2bdc6c606b32a444
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871079"
---
# <a name="step-5-deploy-windows-10-enterprise-security-features"></a>Шаг 5: Развертывание компонентов безопасности Windows 10 Enterprise

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Windows 10 предоставляет функции защиты от угроз, Справка защиты устройство и помощь в управлении доступом. 

Для получения дополнительных сведений об этих технологий, см.
* [Защиты доступа](https://docs.microsoft.com/windows/access-protection/) — сведения о доступа управления S/MIME, цифровые сертификаты, защиты учетных данных, контроль учетных записей пользователей, виртуальные разумная карты, Windows Hello для бизнеса, брандмауэр Windows в режиме повышенной безопасности и др.
* [Защита устройств](https://docs.microsoft.com/windows/device-security/) - включает в себя AppLocker, BitLocker, устройство защиты и модуль
* [Защиту от угроз](https://docs.microsoft.com/windows/threat-protection/) - включает в себя Защитник центр обеспечения безопасности, защиту от угроз дополнительные Защитника Windows, антивирусная программа Защитник Windows, Guard приложения Защитник Windows, экран смарт-Защитника Windows и защита информации Windows

Это действие показано, как можно развернуть, управление, Настройка и устранение неполадок при использовании этих функций безопасности:

* [Антивирусная программа "Защитник Windows"](#windows-defender-antivirus)
* [Exploit Guard в Защитнике Windows](#windows-defender-exploit-guard)
* [Advanced Threat Protection в Защитнике Windows](#windows-defender-advanced-threat-protection)

<a name="windows10-sec-av"></a>
## <a name="windows-defender-antivirus"></a>Антивирусная программа "Защитник Windows"
Защита от вирусов Защитника Windows (AV) — это решение защиты от вредоносных программ, встроенной в Windows 10. Предоставляет безопасности и защиты от вредоносных программ управления для настольных компьютеров, переносными компьютерами и серверами. Дополнительные сведения о аудио/видео Защитника Windows, минимальные требования и как можно управлять этой функции в разделе [Защита от вирусов Защитника Windows в Windows 10 и Windows Server 2016](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10).

Если вы не используете аудио/видео Защитника Windows как основной антивирусного клиента или при использовании также ATP Защитника Windows, существуют некоторые соображения необходимо учитывать для учетной записи. Для получения дополнительных сведений см [совместимости аудио/видео Защитника Windows](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-compatibility).

### <a name="deployment-and-management"></a>Развертывание и управление ими
Для развертывания и управления AV Защитника Windows, следуйте рекомендациям в статье:

* [Развертывание, управление и создание отчетов по аудио/видео Защитника Windows](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [Ссылки на разделы средства управления и конфигурации](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

### <a name="configuration"></a>Конфигурация
Пользователи могут настраивать ряд возможностей. Дополнительные сведения см.

* [Настройка функций аудио/видео Защитника Windows](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)
* [Ссылки на разделы средства управления и конфигурации](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

Чтобы облегчить понимание параметров конфигурации, обратитесь в этот список всех параметров (как определено их конфигурации групповой политики): [Параметры использования групповой политики для настройки и управления AV Защитника Windows](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/use-group-policy-windows-defender-antivirus)

Можно использовать [аудио/видео Защитник Windows защиты руководство по оценке](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/evaluate-windows-defender-antivirus) помогут оценить уровень защиты и влияние аудио/видео Защитника Windows в сети. Это также может быть полезна при создании начальной настройки или как «quick start guide» и регулярно обновляемый для обеспечения наиболее полезен рекомендации по настройке и включение средств для обеспечения максимальной защиты.

### <a name="reporting"></a>Отчеты
Вы можете обеспечить создание отчетов с помощью средства настройки, такие как System Center Configuration Manager или Microsoft Intune. Можно также получить отчетов из соответствия требованиям обновления (OMS) или основе журналов событий Windows в вашей SIEM. При наличии лицензии для анализа Защитник Windows можно получить отчетов в обнаружения аудио/видео Защитника Windows и выполнять основные исправления. Дополнительные сведения см.
* [Развертывание, управление и создание отчетов по аудио/видео Защитника Windows](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [Создание отчетов по защите аудио/видео Защитника Windows](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/report-monitor-windows-defender-antivirus)
* [Обзор портала ATP Защитника Windows](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>Устранение неполадок
Сведения о базовых устранения неполадок кодов ошибок и событий в разделе [Журналы просмотра событий и коды ошибок для устранения проблемы, связанные с AV Защитника Windows](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus).

Также можно отправлять проблемы (например, ложные срабатывания), используя систему отправки аналитики безопасности Защитника Windows. Чтобы узнать, как просмотреть [проблемы отправить в корпорацию Майкрософт](https://www.microsoft.com/wdsi/filesubmission).

<a name="windows10-sec-eg"></a>
## <a name="windows-defender-exploit-guard"></a>Exploit Guard в Защитнике Windows
Защита воспользоваться Защитник Windows — это новый набор возможностей предотвращения обнаружение вторжений узла для Windows 10. Дополнительные сведения о Guard воспользоваться Защитника Windows, минимальные требования и как можно управлять этой функции в разделе [Защита воспользоваться Защитника Windows](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard).

### <a name="deployment-management-and-configuration"></a>Развертывания, управления и конфигурации
Для развертывания, управления и настройки защиты воспользоваться Защитника Windows, следуйте рекомендациям в статье здесь:
* [Воспользоваться защиты](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/exploit-protection-exploit-guard)
* [Защита поверхности атаки](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard?ocid=cx-docs-msa4053440)
* [Защита сети](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/network-protection-exploit-guard)
* [Управляет доступом к папке](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard)

Можно использовать ряд оценки разделы помогут оценить уровень защиты и влияние системы безопасности воспользоваться Защитника Windows в сети. Это также может быть полезна при создании начальной настройки или как «quick start guide» и разделы и рекомендации для обеспечения наиболее полезен рекомендации по настройке и включение средств для обеспечения максимальной защиты регулярно обновляемый. Дополнительные сведения, [Оценка Guard воспользоваться Защитника Windows](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/evaluate-windows-defender-exploit-guard).

### <a name="reporting"></a>Отчеты
Создание отчетов с помощью средства настройки, такие как System Center Configuration Manager или Intune можно получить. Можно также получить, создание отчетов с использования журналов событий Windows в вашей SIEM. При наличии лицензии для анализа Защитник Windows можно получить отчетов в обнаружения аудио/видео Защитника Windows и выполнять основные исправления. Дополнительные сведения см.
* [Просмотр событий Guard воспользоваться Защитника Windows](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/event-views-exploit-guard)
* [Обзор портала ATP Защитника Windows](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>Устранение неполадок
Выполните основные способы устранения неполадок или при необходимости предоставлять корпорации Microsoft CAB-файлы и отправка вопросов (например, ложные срабатывания), используя систему отправки аналитики безопасности Защитника Windows. Чтобы узнать, как просмотреть [проблемы отправить в корпорацию Майкрософт](https://www.microsoft.com/wdsi/filesubmission).


<a name="windows10-sec-atp"></a>
## <a name="windows-defender-advanced-threat-protection"></a>Advanced Threat Protection в Защитнике Windows
ATP Защитника Windows, доступны только в плане Microsoft 365 Enterprise E5 — это служба безопасности, которая позволяет корпоративным клиентам обнаруживать, исследовать и реагировать на дополнительные угрозы, связанные с сети, на. Дополнительные сведения о ATP Защитник Windows минимальным требованиям, и как можно управлять этой функции можно найти:

* [ATP в Защитнике Windows](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)
* [Минимальные требования](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/minimum-requirements-windows-defender-advanced-threat-protection)

### <a name="deployment-management-and-configuration"></a>Развертывания, управления и конфигурации
Чтобы развернуть ATP Защитника Windows, вам потребуется убедитесь, что вы имеете право лицензии Windows. После проверки на наличие правом лицензии, необходимо решить, географического расположения для хранения данных. После этого можно запустить конечные точки адаптация новых сотрудников в службу.

Для получения дополнительных сведений о эти действия основного см. 

* [Проверка подготовки лицензии и завершения настройки](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/licensing-windows-defender-advanced-threat-protection)
* [Хранилище данных и конфиденциальности](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/data-storage-privacy-windows-defender-advanced-threat-protection)
* [Встроенный конечные точки и установка access](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/onboard-configure-windows-defender-advanced-threat-protection)

### <a name="detect-investigate-respond"></a>Определить, исследовать, ответ
После успешного входящая конечных точек в службу можно начать исследование оповещений из различных панелей мониторинга. Как только изучению оповещения, могут выполнять действия ответа на оповещения. 

Приведены дополнительные сведения о том, как выполните следующие действия:
* [Обзор портала ATP Защитника Windows](https://go.microsoft.com/fwlink/?linkid=861596)
* [Использование портала ATP Защитника Windows](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-windows-defender-advanced-threat-protection)
* [Выполните действия ответа](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/response-actions-windows-defender-advanced-threat-protection)

### <a name="integrate-with-other-products-and-tools"></a>Интеграция с другими продуктами и средств
ATP Защитник Windows объединяет и поддерживает различные продукты и средства для расширения его возможностей безопасности. 

Дополнительные сведения о средствах и других продуктов см.
* [Средства SIEM](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/configure-siem-windows-defender-advanced-threat-protection)
* [Создание настраиваемых оповещений](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-custom-ti-windows-defender-advanced-threat-protection)
* [Использование интерфейсов API](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/exposed-apis-windows-defender-advanced-threat-protection)
* [Создание отчетов Power BI](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/powerbi-reports-windows-defender-advanced-threat-protection)

### <a name="troubleshooting"></a>Устранение неполадок
Могут возникать проблемы при адаптация новых сотрудников или во время использования продукта. Дополнительные сведения о способах устранения проблем см.
* [Устранение неполадок адаптация новых сотрудников](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-onboarding-windows-defender-advanced-threat-protection)
* [Устранение неполадок Защитник Windows ATP](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-windows-defender-advanced-threat-protection)

## <a name="next-step"></a>Следующее действие

[Выходные условия инфраструктуры Windows 10 Enterprise](windows10-exit-criteria.md)
