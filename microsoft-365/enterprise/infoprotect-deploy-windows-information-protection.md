---
title: Шаг 4. Настройка Windows Information Protection
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
ms.openlocfilehash: b624db45c4fe3bd75b2158f225176b7a78ba30f8
ms.sourcegitcommit: 63e35b846d964dde5919a08c2fe432e749e8eff6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2019
ms.locfileid: "37047272"
---
# <a name="step-4-configure-windows-information-protection"></a>Шаг 4. Настройка Windows Information Protection

*Этот шаг необязательный; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Чем больше персональных устройств используется для работы, тем выше становится риск утечки конфиденциальных данных организаций через приложения и устройства. Например, сотрудник может случайно отправить на сайт социальной сети рисунок с маркетинговым планом будущего продукта или сохранить в общедоступном облачном хранилище файл, содержащий совершенно секретную информацию. 

Windows Information Protection (WIP) обеспечивает защиту от утечки данных такого рода на устройствах с Windows 10. Дополнительные сведения см. в статье [Защита корпоративных данных с помощью WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).

В Microsoft 365 корпоративный WIP представляет собой сочетание операционной системы Windows 10 Корпоративная и службы Microsoft Intune, которая входит в вашу подписку. 

Для развертывания WIP в организации с использованием Microsoft 365 корпоративный выполните следующие действия.

1. Зарегистрируйте свои устройства Windows в Intune. Это уже должно быть сделано на [Шаге 5. Управление мобильными устройствами](mobility-infrastructure.md).
2. Создайте [политику Intune для WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure).
  - Убедитесь, что список защищенных приложений заполнен.
  - Выберите уровень защиты WIP.

Также можно использовать WIP с [System Center Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/overview-create-wip-policy-sccm). 

Дополнительную информацию см. в статье [Советы и рекомендации по WIP]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip).

Прежде чем перейти к следующему шагу, проверьте [условия](infoprotect-exit-criteria.md#crit-infoprotect-step4), при выполнении которых можно считать данный шаг завершенным.

## <a name="next-step"></a>Следующее действие

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[Настройка защиты от потери данных Office 365](infoprotect-data-loss-prevention.md)|


