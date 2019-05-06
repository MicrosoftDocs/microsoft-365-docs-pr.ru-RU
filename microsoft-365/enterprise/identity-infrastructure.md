---
title: Шаг 2. Идентификация
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/16/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: В этом разделе рассказывается, как развернуть инфраструктуру идентификации для Microsoft 365 корпоративный.
ms.openlocfilehash: 932b6fb2cfeb86edcf708bdfdea55cdd8b580838
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288744"
---
# <a name="phase-2-identity"></a>Шаг 2. Идентификация

![](./media/deploy-foundation-infrastructure/identity_icon.png)

В Microsoft 365 корпоративный хорошо спланированная и реализованная инфраструктура идентификации позволяет усилить защиту и предоставлять доступ к рабочим нагрузкам и их данным только пользователям и устройствам, прошедшим проверку подлинности.

>[!Note]
>Если вы уже развернули инфраструктуру идентификации, см. перечень обязательных и необязательных [условий](identity-exit-criteria.md), при выполнении которых можно считать инфраструктуру идентификации для Microsoft 365 корпоративный настроенной.
>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a>Планирование и развертывание инфраструктуры идентификации Microsoft 365 корпоративный 

Перед началом работы посмотрите это видео с обзором моделей удостоверений и проверки подлинности для Microsoft 365.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

Выполните указанные ниже шаги, чтобы спланировать и развернуть новую инфраструктуру идентификации в облаке. Кроме того, с помощью этих шагов можно адаптировать имеющуюся у вас локальную или гибридную инфраструктуру идентификации для работы с Microsoft 365 корпоративный. 

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [Планирование пользователей и групп](identity-plan-users-groups.md) |
|![](./media/stepnumbers/Step2.png)| [Защита привилегированных удостоверений](identity-designate-protect-admin-accounts.md) |
|![](./media/stepnumbers/Step3.png)| [Настройка гибридного удостоверения](identity-azure-ad-connect.md) |
|![](./media/stepnumbers/Step4.png)| [Настройка безопасной проверки подлинности пользователей](identity-multi-factor-authentication.md) |
|![](./media/stepnumbers/Step5.png)| [Упрощение доступа для пользователей](identity-password-reset.md) |
|![](./media/stepnumbers/Step6.png)| [Упрощение управления с помощью групп](identity-self-service-group-management.md) |

Выполнив эти шаги, перейдите к перечню обязательных и необязательных [условий](identity-exit-criteria.md) для соответствия требованиям Microsoft 365 корпоративный, при выполнении которых можно считать данный шаг завершенным.

## <a name="identity-and-device-access-recommendations"></a>Рекомендации по доступу для удостоверений и устройств

Корпорация Майкрософт предоставляет набор рекомендаций по [доступу для удостоверений и устройств ](microsoft-365-policies-configurations.md), обеспечивая тем самым безопасность и эффективность рабочих ресурсов. Для работы с удостоверениями вместе с действиями, указанными на этом этапе, используйте рекомендации и параметры, изложенные в следующих статьях:

- [Необходимые компоненты](identity-access-prerequisites.md)
- [Основные политики доступа для удостоверений и устройств](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Как корпорация Майкрософт реализует Microsoft 365 корпоративный

Узнайте, как ИТ-специалисты корпорации Майкрософт спланировали и развернули возможности работы с удостоверениями в Microsoft 365 корпоративный, из следующих ресурсов:

- [Управление удостоверениями пользователей и защита доступа в корпорации Майкрософт](https://www.microsoft.com/itshowcase/Article/Content/931/Managing-user-identities-and-secure-access-at-Microsoft)
- [Использование Azure AD Privileged Identity Management для повышения прав доступа](https://www.microsoft.com/itshowcase/Article/Content/887/Using-Azure-AD-Privileged-Identity-Management-for-elevated-access)

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Как корпорация Contoso реализовала Microsoft 365 корпоративный

Посмотрите, как Contoso, вымышленная, но типичная многонациональная корпорация, [развернула инфраструктуру гибридных удостоверений](contoso-identity.md) для облачных служб Microsoft 365.

![](./media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a>Следующий шаг

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [Планирование пользователей и групп](identity-plan-users-groups.md) |
