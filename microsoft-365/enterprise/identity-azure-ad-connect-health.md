---
title: Шаг 8. Отслеживание работоспособности функции синхронизации
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: В этой статье рассказывается, как настроить Azure AD Connect Health.
ms.openlocfilehash: 21cfd88617bccab3f0a2bdb51c0d320cd4568a56
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870861"
---
# <a name="step-8-monitor-synchronization-health"></a>Шаг 8. Отслеживание работоспособности функции синхронизации

*Этот шаг — необязательный; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

На этом шаге вы установите агент Azure AD Connect Health на все свои локальные серверы удостоверений, чтобы отслеживать инфраструктуру идентификации и службы синхронизации, предоставляемые Azure AD Connect. Сведения, полученные в результате мониторинга, доступны на портале Azure AD Connect Health. Там вы можете просматривать предупреждения, результаты мониторинга производительности, аналитические данные об использовании и прочие сведения.

![Компоненты Azure AD Connect Health](./media/identity-azure-ad-connect-health/identity-azure-ad-connect-health.png)

Ключевое решение о способе использования Azure AD Connect Health зависит от способа, которым вы используете Azure AD Connect.

- Если вы используете **управляемую проверку подлинности**, начните работу с прочтения статьи [Мониторинг синхронизации Azure AD Connect с помощью Azure AD Connect Health](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync), чтобы понять и настроить Azure AD Connect Health.
- Если вы синхронизируете только имена учетных записей и групп, используя **федеративную проверку подлинности** с помощью служб федерации Active Directory (AD FS), для начала прочитайте статью [Мониторинг AD FS с помощью Azure AD Connect Health](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs), чтобы понять и настроить Azure AD Connect Health.

Когда вы завершите этот этап, у вас будут указанные ниже элементы.

- На каждом из ваших локальных серверов поставщиков удостоверений установлен агент Azure AD Connect Health.
- На портале Azure AD Connect Health отображается текущее состояние вашей локальной инфраструктуры и действий по синхронизации с клиентом Azure AD для ваших подписок Office 365 и EMS.

Прежде чем перейти к следующему шагу, проверьте [условия](identity-exit-criteria.md#crit-identity-sync-health), при выполнении которых можно считать данный шаг завершенным.


## <a name="next-step"></a>Следующий шаг

|||
|:-------|:-----|
|![](./media/stepnumbers/Step9.png)| [Упрощение процедуры обновления паролей](identity-password-writeback.md) |

