---
title: Настройка политик условного доступа для кампаний Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Узнайте, как настроить политики условного доступа для кампаний Microsoft 365, чтобы добавить существенную дополнительную защиту.
ms.openlocfilehash: 58ee760877ee2fd7e53ef9463242657ab66a2b6e
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2020
ms.locfileid: "44470654"
---
# <a name="set-up-conditional-access-policies"></a>Настройка политик условного доступа

Эта статья относится к Microsoft 365 Business Premium.

Политики [условного доступа](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) добавляют существенную дополнительную защиту. Корпорация Майкрософт предоставляет набор базовых политик условного доступа, рекомендуемых для всех клиентов. Базовые политики это набор предопределенных политик, которые помогают защитить организации от многих распространенных атак. Эти распространенные атаки могут включать распылителя, преобразования и фишинга паролей.

Эти политики требуют, чтобы администраторы и пользователи вводили вторую форму проверки подлинности (называемую многофакторной проверкой подлинности или MFA) при выполнении определенных условий. Например, если пользователь входит в другую страну, то вход может считаться рискованным и пользователь должен предоставить дополнительную форму проверки подлинности. 

В настоящее время базовые политики включают следующее:
- **Требовать MFA для администраторов** &ndash; Требует многофакторной проверки подлинности для наиболее привилегированных ролей администратора, в том числе глобального администратора.
- **Защита от** &ndash; конечных пользователей Требует многофакторной проверки подлинности для пользователей, только если вход в систему рискованный. 
- **Блокировать устаревшую проверку подлинности** &ndash; Старые клиентские приложения и некоторые новые приложения не используют новые, более безопасные протоколы проверки подлинности. Эти старые приложения могут обходить политики условного доступа и получать несанкционированный доступ к вашей среде. Эта политика блокирует доступ клиентов, не поддерживающих условный доступ. 
- **Запрос MFA для управления службами** &ndash; Требует многофакторной проверки подлинности для доступа к средствам управления, включая портал Azure (при настройке базовых политик). 

Корпорация Майкрософт рекомендует включить все эти базовые политики. После включения этих политик Администраторы и пользователи будут получать запросы на регистрацию для проверки подлинности Azure Мултии.

Для получения дополнительных сведений об этих политиках, ознакомьтесь со статьями [базовых политик](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)


## <a name="set-up-baseline-policies"></a>Настройка базовых политик

1. Перейдите на [портал Azure](https://portal.azure.com), а затем перейдите к **Azure Active Directory** \> **условному доступу**к Azure Active Directory.
    
    Базовые политики перечислены на странице. <br/> <br/>
    ![Страница, на которой перечисляются базовые политики для условного доступа.](../media/baslinepolicies.png)
1. Для каждой политики ознакомьтесь с приведенными ниже инструкциями.

  - [Требовать MFA для администраторов](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [Требовать MFA для пользователей](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [Блокирование традиционной проверки подлинности](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [Запрос MFA для управления службами](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

Можно настроить множество дополнительных политик, например требование утвержденных клиентских приложений. Дополнительные сведения см. в [документации по условному доступу](https://docs.microsoft.com/azure/active-directory/conditional-access/).
