---
title: Шаг 4. Настройка Windows Information Protection
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Изучение и развертывание Windows Information Protection в Microsoft 365.
ms.openlocfilehash: 66c9e10772edb0782096ba120858e895684255b2
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631649"
---
# <a name="step-4-configure-windows-information-protection"></a>Шаг 4. Настройка Windows Information Protection

*Этот этап не является обязательным. Он применяется к планам E3 и E5 Microsoft 365 корпоративный.*

![Этап 6. Защита данных](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Чем больше персональных устройств используется для работы, тем выше становится риск утечки конфиденциальных данных организаций через приложения и устройства. Например, сотрудник может случайно отправить на сайт социальной сети рисунок с маркетинговым планом будущего продукта или сохранить в общедоступном облачном хранилище файл, содержащий совершенно секретную информацию. 

Windows Information Protection (WIP) обеспечивает защиту от утечки данных такого рода на устройствах с Windows 10. Дополнительные сведения см. в статье [Защита корпоративных данных с помощью WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).

В Microsoft 365 корпоративный WIP представляет собой сочетание операционной системы Windows 10 Корпоративная и службы Microsoft Intune, которая входит в вашу подписку. 

Для развертывания WIP в организации с использованием Microsoft 365 корпоративный выполните следующие действия.

1. Зарегистрируйте свои устройства Windows в Intune. Это уже должно быть сделано на [Этапе 5. Управление мобильными устройствами](mobility-infrastructure.md).
2. Создайте [политику Intune для WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure).
  - Убедитесь, что список защищенных приложений заполнен.
  - Выберите уровень защиты WIP.

Также можно использовать WIP с [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/overview-create-wip-policy-sccm). 

Дополнительную информацию см. в статье [Советы и рекомендации по WIP]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip).

Прежде чем перейти к следующему шагу, проверьте [условия](infoprotect-exit-criteria.md#crit-infoprotect-step4), при выполнении которых можно считать данный шаг завершенным.

## <a name="next-step"></a>Следующий шаг

|||
|:-------|:-----|
|![Шаг 5](../media/stepnumbers/Step5.png)|[Настройка защиты от потери данных](infoprotect-data-loss-prevention.md)|


