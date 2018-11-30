---
title: Шаг 14. Разрешение пользователям создавать собственные группы и управлять ими
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
description: В этом разделе рассказывается, как настроить самостоятельное управление группами Azure AD.
ms.openlocfilehash: d46e82fd72b8eef896a223229a2cc3d25ae56c76
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870768"
---
# <a name="step-14-allow-users-to-create-and-manage-their-own-groups"></a>Шаг 14. Разрешение пользователям создавать собственные группы и управлять ими

*Этот шаг — необязательный; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

На этом шаге вы определите группы Azure Active Directory (AD), которыми могут управлять владельцы этих групп (вместо ИТ-администраторов). Эта функция, называемая *самостоятельное управление группами*, позволяет владельцам групп, которым не назначена административная роль, создавать группы безопасности и управлять ими. 

Пользователи могут запрашивать членство в группе безопасности, и такие запросы будут поступать владельцу группы, а не ИТ-администратору. Это позволяет делегировать повседневный контроль членства в группе владельцам группы, проекта или организации, которые понимают бизнес-цель группы и могут управлять членством в ней.

>[!Note]
>Функция самостоятельного управления группами доступна только для защиты Azure AD и групп Office 365. Она недоступна для групп, поддерживающих почту, списков рассылки и всех групп, которые были синхронизированы из вашего локального Windows Server Active Directory (AD).
>

Дополнительные сведения см. в статье с [инструкциями по настройке групп Azure AD для самостоятельного управления группами](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).

Прежде чем перейти к следующему шагу, проверьте [условия](identity-exit-criteria.md#crit-identity-self-service-groups), при выполнении которых можно считать данный шаг завершенным.

## <a name="next-step"></a>Следующий шаг

|||
|:-------|:-----|
|![](./media/stepnumbers/Step15.png)| [Настройка динамического членства в группах](identity-automatic-group-membership.md) |
