---
title: Этап 2. Идентификация
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: В этом разделе рассказывается, как развернуть инфраструктуру идентификации для Microsoft 365 корпоративный.
ms.openlocfilehash: cb5b714afcacd1e21951ec9f83fd7f09cbd88662
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370446"
---
# <a name="phase-2-identity"></a>Этап 2. Идентификация

![Этап 2. Идентификация](./media/deploy-foundation-infrastructure/identity_icon.png)

В Microsoft 365 корпоративный хорошо спланированная и реализованная инфраструктура идентификации позволяет усилить защиту и предоставлять доступ к рабочим нагрузкам и их данным только пользователям и устройствам, прошедшим проверку подлинности.

Просмотрите это видео с обзором моделей удостоверений и проверки подлинности для Microsoft 365 корпоративный.

<p> </p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

>[!Note]
>Если вы уже развернули инфраструктуру идентификации, см. перечень обязательных и необязательных [условий](identity-exit-criteria.md), при выполнении которых можно считать инфраструктуру идентификации для Microsoft 365 корпоративный настроенной.
>

Сведения о функциях удостоверений для каждого плана Microsoft 365 корпоративный, роли Azure Active Directory (Azure AD), локальных и облачных компонентах, а также самых распространенных настройках проверки подлинности см. на [плакате инфраструктуры удостоверений](media/identity-infrastructure/M365E-ID-Infra.pdf).

[![Плакат инфраструктуры удостоверений](./media/identity-infrastructure/m365e-identity-arch-poster.png)](media/identity-infrastructure/M365E-ID-Infra.pdf)

Эту двухстраничный плакат позволяет быстро ознакомиться с основными понятиями и настройками Microsoft 365 корпоративный.

Вы также можете [скачать этот плакат](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/identity-infrastructure/M365E-ID-Infra.pdf) и распечатать его в формате письма, юридического документа или газетном формате (11 х 17).

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a>Планирование и развертывание инфраструктуры идентификации Microsoft 365 корпоративный 

Выполните указанные ниже шаги, чтобы спланировать и развернуть новую инфраструктуру идентификации в облаке. Кроме того, с помощью этих шагов можно адаптировать имеющуюся у вас локальную или гибридную инфраструктуру идентификации для работы с Microsoft 365 корпоративный. 

|||
|:-------|:-----|
|![Шаг 1](./media/stepnumbers/Step1.png)| [Создание и защита учетных записей глобальных администраторов](identity-create-protect-global-admins.md) |
|![Шаг 2](./media/stepnumbers/Step2.png)| [Защита паролей](identity-secure-your-passwords.md) |
|![Шаг 3](./media/stepnumbers/Step3.png)| [Защита пользовательских входов и управление ими](identity-secure-user-sign-ins.md) |
|![Шаг 4](./media/stepnumbers/Step4.png)| [Добавление учетных записей пользователей](identity-add-user-accounts.md) |
|![Шаг 5](./media/stepnumbers/Step5.png)| [Управление с помощью групп](identity-use-group-management.md) |
|![Шаг 6](./media/stepnumbers/Step6.png)| [Настройка управления удостоверениями](identity-configure-identity-governance.md) |

Выполнив эти шаги, перейдите к перечню обязательных и необязательных [условий](identity-exit-criteria.md) для соответствия требованиям к удостоверениям Microsoft 365 корпоративный, при выполнении которых можно считать данный шаг завершенным.

## <a name="identity-and-device-access-recommendations"></a>Рекомендации по доступу для удостоверений и устройств

Корпорация Майкрософт предоставляет набор рекомендаций по [доступу для удостоверений и устройств ](microsoft-365-policies-configurations.md), обеспечивая тем самым безопасность и эффективность рабочих ресурсов. Для работы с удостоверениями вместе с действиями, указанными на этом этапе, используйте рекомендации и параметры, изложенные в следующих статьях:

- [Необходимые компоненты](identity-access-prerequisites.md)
- [Основные политики доступа для удостоверений и устройств](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Как корпорация Майкрософт реализует Microsoft 365 корпоративный

Узнайте, как ИТ-специалисты в корпорации Майкрософт [управляют удостоверениями и обеспечивают безопасный доступ](https://www.microsoft.com/ru-RU/itshowcase/deploying-and-managing-microsoft-365#primaryR5).

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Как корпорация Contoso реализовала Microsoft 365 корпоративный

Посмотрите, как Contoso, вымышленная, но типичная многонациональная корпорация, [развернула инфраструктуру гибридных удостоверений](contoso-identity.md) для облачных служб Microsoft 365.

![Корпорация Contoso](./media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a>Следующий шаг

|||
|:-------|:-----|
|![Шаг 1](./media/stepnumbers/Step1.png)| [Создание и защита учетных записей глобальных администраторов](identity-create-protect-global-admins.md) |
