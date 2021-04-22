---
title: Оптимизация развертывания и обнаружений правил сокращения направлений атак
description: Оптимизируйте правила уменьшения поверхности атаки для выявления и предотвращения типичных эксплойтов вредоносных программ.
keywords: onboard, Управление Intune, Microsoft Defender для endpoint, Microsoft Defender, Защитник Windows, уменьшение поверхности атаки, ASR, базовый уровень безопасности
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
ms.openlocfilehash: 91295135c833c6b403078bdfd517c7b84ec7d630
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932851"
---
# <a name="optimize-asr-rule-deployment-and-detections"></a>Оптимизация развертывания и обнаружений правил сокращения направлений атак

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

[Правила уменьшения поверхности атаки (ASR) определяют](./attack-surface-reduction.md) и предотвращают типичные эксплойты вредоносных программ. Они контролируют, когда и как может запускаться потенциально вредоносный код. Например, они могут запретить JavaScript или VBScript запускать скачаемый исполняемый файл, блокировать вызовы API Win32 из макроса Office и блокировать процессы, запускаемые с USB-дисков.

![Карта управления поверхностью атаки](images/secconmgmt_asr_card.png)<br>
*Карта управления поверхностью атаки*

Карта *управления поверхностью атаки* — это точка входа в средства центра безопасности Microsoft 365, которые можно использовать для:

* Понимание того, как в настоящее время в организации развернуты правила ASR.
* Просмотрите обнаружение ASR и определите возможные неправильные обнаружения.
* Анализ воздействия исключений и создание списка путей для исключения файлов.

Выберите **Go для** мониторинга мониторинга поверхности & отчетов > правил уменьшения поверхности > добавления  >  **исключений.** Оттуда можно перейти к другим разделам центра безопасности Microsoft 365.

![Добавление вкладки исключений на странице Правила уменьшения поверхности атаки в центре безопасности Microsoft 365](images/secconmgmt_asr_m365exlusions.png)<br>
Вкладка ***Добавление исключений** на странице Правила уменьшения поверхности атаки в центре безопасности Microsoft 365*

> [!NOTE]
> Чтобы получить доступ к центру безопасности Microsoft 365, вам потребуется лицензия Microsoft 365 E3 или E5 и учетная запись, которая имеет определенные роли в Azure Active Directory. [Ознакомьтесь с требуемой лицензией и разрешениями.](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions)

Дополнительные сведения о развертывании правил ASR в центре безопасности Microsoft 365 см. в рубрике Монитор и управление развертыванием и обнаружением правил [ASR.](https://docs.microsoft.com/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections)

**Связанные темы**

* [Убедитесь, что ваши устройства настроены правильно](configure-machines.md)
* [Запись устройств в Microsoft Defender для конечной точки](configure-machines-onboarding.md)
* [Отслеживание соответствия базовому стандарту безопасности Microsoft Defender для конечной точки](configure-machines-security-baseline.md)
