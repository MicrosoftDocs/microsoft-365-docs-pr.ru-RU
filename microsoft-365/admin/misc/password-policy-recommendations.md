---
title: Рекомендации политики паролей
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9fa2539a-2211-41fd-85a0-bc37b9619ca4
description: Узнайте, как обеспечить более надежную защиту организации от атак на пароли, а также почему необходимо запретить распространенные пароли и включить многофакторную проверку подлинности с учетом рисков.
ms.openlocfilehash: 1d6e399acb83751ec6a45eb0c811dedec394127e
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015927"
---
# <a name="password-policy-recommendations"></a>Рекомендации политики паролей
 
As the admin of an organization, you're responsible for setting password policy for users in your organization. Setting password policy can be complicated and confusing, and this article provides recommendations to make your organization more secure against password attacks.
  
Сведения о настройке строка действия паролей Microsoft 365 в организации, см. в статье [Настройка политики срока действия паролей для Microsoft 365](../manage/set-password-expiration-policy.md).

Подробнее о паролях Microsoft 365 см. следующие [статьи по теме](#related-articles).
  
## <a name="understanding-password-recommendations"></a>На чем основаны рекомендации

Рекомендации по выбору паролей основаны на нескольких общих принципах:
  
- **Предотвращение распространенных атак.** Этот принцип предполагает ограничение того, где пользователи могут вводить пароли (известные и надежные устройства с надежными средствами обнаружения вредоносных программ, проверенные сайты) и какие пароли можно использовать (длина и уникальность).

- **Containing successful attacks** Containing successful hacker attacks is about limiting exposure to a specific service, or preventing that damage altogether, if a user's password gets stolen. For example, ensuring that a breach of your social networking credentials doesn't make your bank account vulnerable, or not letting a poorly guarded account accept reset links for an important account.

- **Understanding human nature** Many valid password practices fail in the face of natural human behaviors. Understanding human nature is critical because research shows that almost every rule you impose on your users will result in a weakening of password quality. Length requirements, special character requirements, and password change requirements all result in normalization of passwords, which makes it easier for attackers to guess or crack passwords.

## <a name="password-guidelines-for-administrators"></a>Рекомендации по выбору паролей для администраторов

The primary goal of a more secure password system is password diversity. You want your password policy to contain lots of different and hard to guess passwords. Here are a few recommendations for keeping your organization as secure as possible.
  
- Не увеличивайте минимальную длину паролей (8 символов). Больше не значит лучше.

- Don't require character composition requirements. For example, \*&amp;(^%$

- Не требуйте регулярной смены паролей для учетных записей пользователей.

- Запретите использовать распространенные пароли, чтобы в системе не было самых уязвимых паролей.

- Попросите сотрудников не использовать пароли от рабочих учебных записей для личных целей.

- Потребуйте использования [многофакторной проверки подлинности](../security-and-compliance/set-up-multi-factor-authentication.md).

- Включите запросы многофакторной проверки подлинности с учетом рисков.

### <a name="password-guidance-for-your-users"></a>Рекомендации для пользователей по выбору паролей

Here's some password guidance for users in your organization. Make sure to let your users know about these recommendations and enforce the recommended password policies at the organizational level.
  
- Не используйте такие же пароли, как на других сайтах, или аналогичные им.

- Не используйте в качестве пароля одно слово, например **password**, или частые фразы, например **Iloveyou**.

- Используйте пароли, которые будет сложно угадать даже тем, кто хорошо вас знает. Не включайте в них имена и дни рождения своих родных и друзей, названия любимых групп или фразы, которые вы часто произносите.

## <a name="some-common-approaches-and-their-negative-impacts"></a>Распространенные требования к паролям и их негативное влияние

Описанные ниже принципы управления паролями часто используются в компаниях, но, согласно исследованиям, это зачастую приводит к отрицательным последствиям.
  
### <a name="password-expiration-requirements-for-users"></a>Требования к окончанию срока действия паролей

Password expiration requirements do more harm than good, because these requirements make users select predictable passwords, composed of sequential words and numbers which are closely related to each other. In these cases, the next password can be predicted based on the previous password. Password expiration requirements offer no containment benefits because cyber criminals almost always use credentials as soon as they compromise them.
  
### <a name="requiring-long-passwords"></a>Требование длинных паролей

Password length requirements (greater than about 10 characters) can result in user behavior that is predictable and undesirable. For example, users who are required to have a 16-character password may choose repeating patterns like **fourfourfourfour** or **passwordpassword** that meet the character length requirement but aren't hard to guess. Additionally, length requirements increase the chances that users will adopt other insecure practices, such as writing their passwords down, re-using them, or storing them unencrypted in their documents. To encourage users to think about a unique password, we recommend keeping a reasonable 8-character minimum length requirement. 
  
### <a name="requiring-the-use-of-multiple-character-sets"></a>Требование использования нескольких типов символов

Password complexity requirements reduce key space and cause users to act in predictable ways, doing more harm than good. Most systems enforce some level of password complexity requirements. For example, passwords need characters from all three of the following categories:
  
- прописные буквы;

- строчные буквы;

- небуквенные символы.

Most people use similar patterns, for example, a capital letter in the first position, a symbol in the last, and a number in the last 2. Cyber criminals know this, so they run their dictionary attacks using the most common substitutions, "$" for "s", "@" for "a," "1" for "l". Forcing your users to choose a combination of upper, lower, digits, special characters has a negative effect. Some complexity requirements even prevent users from using secure and memorable passwords, and force them into coming up with less secure and less memorable passwords.
  
## <a name="successful-patterns"></a>Рекомендации

Ниже приведены некоторые рекомендации, которые помогут обеспечить разнообразие паролей.
  
### <a name="ban-common-passwords"></a>Запретите распространенные пароли

The most important password requirement you should put on your users when creating passwords is to ban the use of common passwords to reduce your organization's susceptibility to brute force password attacks. Common user passwords include, **abdcefg**, **password**, **monkey**.
  
### <a name="educate-users-to-not-re-use-organization-passwords-anywhere-else"></a>Попросите сотрудников не использовать пароли организации для других целей

One of the most important messages to get across to users in your organization is to not re-use their organization password anywhere else. The use of organization passwords in external websites greatly increases the likelihood that cyber criminals will compromise these passwords.
  
### <a name="enforce-multi-factor-authentication-registration"></a>Принудительно применяйте многофакторную проверку подлинности

Make sure your users update contact and security information, like an alternate email address, phone number, or a device registered for push notifications, so they can respond to security challenges and be notified of security events. Updated contact and security information helps users verify their identity if they ever forget their password, or if someone else tries to take over their account. It also provides an out of band notification channel in the case of security events such as login attempts or changed passwords. 
  
Дополнительные сведения см. в статье [Настройка многофакторной проверки подлинности](../security-and-compliance/set-up-multi-factor-authentication.md).
  
### <a name="enable-risk-based-multi-factor-authentication"></a>Включите многофакторную проверку подлинности с учетом рисков

Многофакторная проверка подлинности с учетом рисков гарантирует, что если наша система обнаружит подозрительную активность, она выведет запрос, позволяющий убедиться, что действия выполнены владельцем учетной записи. 
  
## <a name="want-to-know-more-recommended-reading"></a>Хотите узнать больше? Рекомендуемая литература

- [К каким результатам приводят надежные пароли?](https://go.microsoft.com/fwlink/p/?linkid=861008) (на английском языке)

- [Портфолио паролей и пользователь с ограниченными усилиями](https://go.microsoft.com/fwlink/p/?linkid=861014) (на английском языке)

- [Предотвращение ненадежных паролей путем прогнозирования действий пользователей](https://go.microsoft.com/fwlink/p/?linkid=861015) (на английском языке)

- [Выбор безопасных паролей](https://go.microsoft.com/fwlink/p/?linkid=861016) (на английском языке)

- [Пора отказаться от обязательной смены паролей](https://go.microsoft.com/fwlink/p/?linkid=861018) (на английском языке)

- [Худшие пароли 2015 г.](https://go.microsoft.com/fwlink/p/?linkid=861020) (на английском языке)

- [Скачивание файлов из Интернета](https://go.microsoft.com/fwlink/p/?linkid=861029)

## <a name="related-articles"></a>Статьи по теме

[Сброс паролей](https://docs.microsoft.com/microsoft-365/admin/add-users/reset-passwords)

[Установка бессрочных пользовательских паролей](https://docs.microsoft.com/microsoft-365/admin/add-users/set-password-to-never-expire)

[Предоставление пользователям прав на самостоятельный сброс пароля](https://docs.microsoft.com/microsoft-365/admin/add-users/let-users-reset-passwords)

[Повторная отправка пароля пользователя. Справка для администраторов](https://docs.microsoft.com/microsoft-365/admin/add-users/resend-user-password)
