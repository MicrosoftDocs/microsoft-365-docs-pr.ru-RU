---
title: Шаг 10. Упрощение входа для пользователей
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: В этой статье рассказывается, как настроить функцию простого единого входа для Azure AD.
ms.openlocfilehash: 9d18cb559d3a4a9ee401e0f94fb53bc6360d88c8
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870982"
---
# <a name="step-10-simplify-user-sign-in"></a>Шаг 10. Упрощение входа для пользователей

*Этот шаг — необязательный для гибридных развертываний; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

На этом шаге вы настроите функцию простого единого входа для Azure Active Directory. Благодаря этой функции ваши пользователи смогут входить в систему в службах, использующих учетные записи пользователей Azure AD, не вводя свои пароли, и, во многих случаях, свои имена пользователей. Это упрощает доступ пользователей к облачным приложениям, например Office 365, без необходимости использовать дополнительные локальные компоненты, например серверы федерации удостоверений.

Вы настроите простой единый вход для Azure AD с помощью средства Azure AD Connect.

См. [инструкции по настройке простого единого входа для Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).

|||
|:-------|:-----|
|![Руководства для лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Руководство по лаборатории тестирования: простой единый вход Azure AD](single-sign-on-m365-ent-test-environment.md) |
|||

Прежде чем перейти к следующему шагу, проверьте [условия](identity-exit-criteria.md#crit-identity-sso), при выполнении которых можно считать данный шаг завершенным.

## <a name="next-step"></a>Следующий шаг

|||
|:-------|:-----|
|![](./media/stepnumbers/Step11.png)| [Настройка страницы входа в Office 365](identity-customize-office-365-sign-in.md) |

