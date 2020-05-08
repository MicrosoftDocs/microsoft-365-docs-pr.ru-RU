---
title: Этап 1. Повышение безопасности входа для удаленных сотрудников с помощью MFA
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- M365solutions
ms.custom: ''
description: Необходимо, чтобы удаленные работники входили в систему с помощью многофакторной проверки подлинности (MFA).
ms.openlocfilehash: 2cb16c78f7fb0b1f9f48559c61a6200d6adcf470
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "44166141"
---
# <a name="step-1-increase-sign-in-security-for-remote-workers-with-mfa"></a>Этап 1. Повышение безопасности входа для удаленных сотрудников с помощью MFA

Чтобы повысить безопасность входа удаленных сотрудников, используйте многофакторную проверку подлинности (MFA). В MFA для входа в систему кроме пароля учетной записи пользователя необходимо использовать дополнительные проверки. Даже если злонамеренный пользователь определит пароль учетной записи пользователя, до получения доступа он должен пройти дополнительные проверки, например ответить на текстовые сообщения, отправленные на смартфон.

![Правильный пароль и дополнительная проверка обеспечивают успешный вход](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

Для всех пользователей, в том числе для удаленных сотрудников и особенно для администраторов, корпорация Майкрософт настоятельно рекомендует использование MFA.

Обеспечить применение пользователями MFA на основе плана Microsoft 365 можно тремя способами.

|План  |Рекомендация  |
|---------|---------|
|Планы Microsoft 365 (без Azure AD Premium P1 или P2)     |[Включите параметры безопасности, по умолчанию заданные в Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults). По умолчанию в параметры безопасности Azure AD входит MFA для пользователей и администраторов.   |
|Microsoft 365 E3 (с Azure AD Premium P1)     | Используйте [Общие политики условного доступа](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) для настройки указанных ниже политик. <br>- [Обязательное использование MFA для администраторов](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br>- [Обязательное использование MFA для всех пользователей](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br> - [Блокирование традиционной проверки подлинности](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)       |
|Microsoft 365 E5 (с Azure AD Premium P2)     | Пользуйтесь преимуществами функции защиты идентификации Azure AD, начните применять [Рекомендуемый набор политики условного доступа и связанных с ней политик](../enterprise/identity-access-policies.md) (Майкрософт), создав две следующие политики.<br> - [Обязательное использование MFA при среднем или высоком риске входа в систему](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br>- [Блокирование клиентов, не поддерживающих современную проверку подлинности](../enterprise/identity-access-policies.md#block-clients-that-dont-support-modern-authentication)<br>- [Необходимость смены пароля для пользователей с высоким риском](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)       |
| | |

## <a name="security-defaults"></a>Параметры безопасности по умолчанию

Параметры безопасности по умолчанию — новая функция в платных и пробных подписках Microsoft 365 и Office 365, появившаяся после 21 октября 2019 г. В этих подписках включены параметры безопасности по умолчанию, что ***обязывает всех пользователей применять MFA в приложении Microsoft Authenticator***.
 
На регистрацию MFA в приложении Microsoft Authenticator с помощью смартфонов у пользователей есть 14 дней с момента первого входа в систему после включения параметров безопасности по умолчанию. По истечении 14 дней пользователь не сможет войти в систему до завершения регистрации MFA.

Применение параметров безопасности по умолчанию гарантирует, что все организации имеют базовый уровень безопасности при входе пользователей в систему, включенный по умолчанию. Вы можете отключить параметры безопасности по умолчанию, если предпочитаете использовать MFA с условным доступом или для отдельных учетных записей.

Дополнительные сведения см. в статье [Обзор параметров безопасности, заданных по умолчанию](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).

## <a name="conditional-access-policies"></a>Политики условного доступа

Политики условного доступа — это набор правил, определяющих условия, в соответствии с которым оценивается и разрешается вход в систему. Например, вы можете создать политику условного доступа, которая устанавливает указанные ниже условия.

- Если имя учетной записи пользователя относится к пользователю, который является администратором для Exchange, пользователей, паролей, системы безопасности, SharePoint или глобальным администратором, то для предоставления доступа требуется применение MFA.

Применить эту политику проще, чем помнить о необходимости настройки отдельных учетных записей пользователей для MFA при их добавлении в число таких администраторов или удалении из этого числа.

Кроме того, вы можете использовать политики условного доступа для более сложных функций, таких как требование выполнения входа с определенного устройства, например ноутбука с Windows 10.

Для использования условного доступа требуется наличие Azure AD Premium P1, который входит в состав Microsoft 365 E3 и E5.

Дополнительные сведения см. в статье [Обзор условного доступа](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).

## <a name="azure-ad-identity-protection-policies"></a>Политики защиты идентификации Azure AD

Политики защиты идентификации Azure AD — это набор правил, определяющих условия, в соответствии с которым оценивается и разрешается вход в систему. Например, вы можете создать политику защиты идентификации Azure AD, которая устанавливает указанные ниже условия.

- Если риск входа в систему определяется как средний или высокий, пользователь должен входить в систему с помощью MFA.

Для использования защиты идентификации Azure AD требуется наличие Azure AD Premium P2, который входит в состав Microsoft 365 E5.

Дополнительные сведения см. в статье [Обзор защиты идентификации Azure AD](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).

## <a name="using-these-methods-together"></a>Совместное использование этих методов

Необходимо иметь в виду следующее:

- Если для вас включены политики условного доступа, вы не можете включить параметры безопасности по умолчанию.
- Если для вас включены параметры безопасности по умолчанию, вы не можете включить никакие политики условного доступа.

Если включены параметры безопасности по умолчанию, всем новым пользователям будет предложено пройти регистрацию в MFA и использовать приложение Microsoft Authenticator. 

В этой таблице показаны результаты использования MFA с параметрами безопасности по умолчанию, политиками условного доступа и индивидуальными параметрами учетных записей пользователей.

|| Включен | Отключено | Дополнительный метод проверки подлинности |
|:-------|:-----|:-------|:-------|
| **Параметры безопасности по умолчанию**  | Невозможно использовать политики условного доступа | Возможно использование политик условного доступа | Приложение Microsoft Authenticator |
| **Политики условного доступа** | Если включена хотя бы одна из них, то включение параметров безопасности по умолчанию невозможно | Если все они выключены, то возможно включение параметров безопасности по умолчанию  | Указываются пользователем во время регистрации MFA  |
||||

## <a name="admin-training-and-technical-resources-for-mfa-and-identity"></a>Учебные материалы и технические ресурсы для администраторов по MFA и удостоверениям

- [Планирование MFA для Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-plan)
- [5 основных способов использования Azure AD в организации удаленной работы](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/top-5-ways-your-azure-ad-can-help-you-enable-remote-work/ba-p/1144691)
- [Планирование и развертывание инфраструктуры удостоверений Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure?view=o365-worldwide#plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure)
- [Учебные видеоматериалы по Azure AD академии Azure](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)
- [Настройте политику регистрации многофакторной проверки подлинности Azure](https://docs.microsoft.com/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)

## <a name="results-of-step-1"></a>Результаты этапа 1

После развертывания MFA пользователи:

- должны использовать MFA для входа в систему.
- должны завершить процесс регистрации в MFA и использовать MFA для всех операций входа.

## <a name="next-step"></a>Следующий этап

Перейдите к [этапу 2](empower-people-to-work-remotely-remote-access.md), чтобы обеспечить удаленный доступ к локальным приложениям и службам.
