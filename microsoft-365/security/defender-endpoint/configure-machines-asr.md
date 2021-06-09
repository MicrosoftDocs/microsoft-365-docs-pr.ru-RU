---
title: Оптимизация развертывания и обнаружений правил сокращения направлений атак
description: Оптимизируйте правила уменьшения поверхности атаки для выявления и предотвращения типичных эксплойтов вредоносных программ.
keywords: на борту, управление Intune, Microsoft Defender для конечной точки, Microsoft Defender, Защитник Windows, уменьшение поверхности атаки, ASR, базовый уровень безопасности
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a5590e62e7838bb9f611320b6d0e5c573b2be084
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841562"
---
# <a name="optimize-asr-rule-deployment-and-detections"></a>Оптимизация развертывания и обнаружений правил сокращения направлений атак

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

[Правила уменьшения поверхности атаки (ASR) определяют](./attack-surface-reduction.md) и предотвращают типичные эксплойты вредоносных программ. Они контролируют, когда и как может запускаться потенциально вредоносный код. Например, они могут запретить JavaScript или VBScript запускать загруженный исполняемый файл, блокировать вызовы API Win32 из макроса Office и блокировать процессы, которые выполняются с USB-дисков.

![Карта управления поверхностью атаки](images/secconmgmt_asr_card.png)<br>
*Карта управления поверхностью атаки*

Карта *управления поверхностью атаки* — это точка входа в инструменты в центре Microsoft 365 безопасности, которые можно использовать для:

* Понимание того, как в настоящее время в организации развернуты правила ASR.
* Просмотрите обнаружение ASR и определите возможные неправильные обнаружения.
* Анализ воздействия исключений и создание списка путей для исключения файлов.

Выберите **Go для** мониторинга мониторинга поверхности & отчетов > правил уменьшения поверхности > добавления  >  **исключений.** Оттуда можно перейти к другим разделам центра Microsoft 365 безопасности.

![Добавление вкладки исключений на странице Правил уменьшения поверхности атаки в центре Microsoft 365 безопасности](images/secconmgmt_asr_m365exlusions.png)<br>
Вкладка ***Добавление исключений** на странице Правил уменьшения поверхности атаки в центре Microsoft 365 безопасности*

> [!NOTE]
> Чтобы получить Microsoft 365 центр безопасности, вам потребуется лицензия Microsoft 365 E3 E5 и учетная запись, которая имеет определенные роли в Azure Active Directory. [Ознакомьтесь с требуемой лицензией и разрешениями.](/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions)

Дополнительные сведения о развертывании правил ASR в центре Microsoft 365 см. в рубрике Монитор и управление развертыванием и обнаружением правил [ASR.](/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections)

**Связанные темы**

* [Убедитесь, что ваши устройства настроены правильно](configure-machines.md)
* [Запись устройств в Microsoft Defender для конечной точки](configure-machines-onboarding.md)
* [Отслеживание соответствия базовому стандарту безопасности Microsoft Defender для конечной точки](configure-machines-security-baseline.md)
