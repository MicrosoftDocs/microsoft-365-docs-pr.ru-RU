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
# <a name="password-policy-recommendations"></a><span data-ttu-id="e278f-103">Рекомендации политики паролей</span><span class="sxs-lookup"><span data-stu-id="e278f-103">Password policy recommendations</span></span>
 
<span data-ttu-id="e278f-104">As the admin of an organization, you're responsible for setting password policy for users in your organization.</span><span class="sxs-lookup"><span data-stu-id="e278f-104">As the admin of an organization, you're responsible for setting password policy for users in your organization.</span></span> <span data-ttu-id="e278f-105">Setting password policy can be complicated and confusing, and this article provides recommendations to make your organization more secure against password attacks.</span><span class="sxs-lookup"><span data-stu-id="e278f-105">Setting password policy can be complicated and confusing, and this article provides recommendations to make your organization more secure against password attacks.</span></span>
  
<span data-ttu-id="e278f-106">Сведения о настройке строка действия паролей Microsoft 365 в организации, см. в статье [Настройка политики срока действия паролей для Microsoft 365](../manage/set-password-expiration-policy.md).</span><span class="sxs-lookup"><span data-stu-id="e278f-106">To determine how often Microsoft 365 passwords expire in your organization, see [Set password expiration policy for Microsoft 365](../manage/set-password-expiration-policy.md).</span></span>

<span data-ttu-id="e278f-107">Подробнее о паролях Microsoft 365 см. следующие [статьи по теме](#related-articles).</span><span class="sxs-lookup"><span data-stu-id="e278f-107">For more information about Microsoft 365 passwords, see these [related articles](#related-articles).</span></span>
  
## <a name="understanding-password-recommendations"></a><span data-ttu-id="e278f-108">На чем основаны рекомендации</span><span class="sxs-lookup"><span data-stu-id="e278f-108">Understanding password recommendations</span></span>

<span data-ttu-id="e278f-109">Рекомендации по выбору паролей основаны на нескольких общих принципах:</span><span class="sxs-lookup"><span data-stu-id="e278f-109">Good password practices fall into a few broad categories:</span></span>
  
- <span data-ttu-id="e278f-110">**Предотвращение распространенных атак.** Этот принцип предполагает ограничение того, где пользователи могут вводить пароли (известные и надежные устройства с надежными средствами обнаружения вредоносных программ, проверенные сайты) и какие пароли можно использовать (длина и уникальность).</span><span class="sxs-lookup"><span data-stu-id="e278f-110">**Resisting common attacks** This involves the choice of where users enter passwords (known and trusted devices with good malware detection, validated sites), and the choice of what password to choose (length and uniqueness).</span></span>

- <span data-ttu-id="e278f-111">**Containing successful attacks** Containing successful hacker attacks is about limiting exposure to a specific service, or preventing that damage altogether, if a user's password gets stolen.</span><span class="sxs-lookup"><span data-stu-id="e278f-111">**Containing successful attacks** Containing successful hacker attacks is about limiting exposure to a specific service, or preventing that damage altogether, if a user's password gets stolen.</span></span> <span data-ttu-id="e278f-112">For example, ensuring that a breach of your social networking credentials doesn't make your bank account vulnerable, or not letting a poorly guarded account accept reset links for an important account.</span><span class="sxs-lookup"><span data-stu-id="e278f-112">For example, ensuring that a breach of your social networking credentials doesn't make your bank account vulnerable, or not letting a poorly guarded account accept reset links for an important account.</span></span>

- <span data-ttu-id="e278f-113">**Understanding human nature** Many valid password practices fail in the face of natural human behaviors.</span><span class="sxs-lookup"><span data-stu-id="e278f-113">**Understanding human nature** Many valid password practices fail in the face of natural human behaviors.</span></span> <span data-ttu-id="e278f-114">Understanding human nature is critical because research shows that almost every rule you impose on your users will result in a weakening of password quality.</span><span class="sxs-lookup"><span data-stu-id="e278f-114">Understanding human nature is critical because research shows that almost every rule you impose on your users will result in a weakening of password quality.</span></span> <span data-ttu-id="e278f-115">Length requirements, special character requirements, and password change requirements all result in normalization of passwords, which makes it easier for attackers to guess or crack passwords.</span><span class="sxs-lookup"><span data-stu-id="e278f-115">Length requirements, special character requirements, and password change requirements all result in normalization of passwords, which makes it easier for attackers to guess or crack passwords.</span></span>

## <a name="password-guidelines-for-administrators"></a><span data-ttu-id="e278f-116">Рекомендации по выбору паролей для администраторов</span><span class="sxs-lookup"><span data-stu-id="e278f-116">Password guidelines for administrators</span></span>

<span data-ttu-id="e278f-117">The primary goal of a more secure password system is password diversity.</span><span class="sxs-lookup"><span data-stu-id="e278f-117">The primary goal of a more secure password system is password diversity.</span></span> <span data-ttu-id="e278f-118">You want your password policy to contain lots of different and hard to guess passwords.</span><span class="sxs-lookup"><span data-stu-id="e278f-118">You want your password policy to contain lots of different and hard to guess passwords.</span></span> <span data-ttu-id="e278f-119">Here are a few recommendations for keeping your organization as secure as possible.</span><span class="sxs-lookup"><span data-stu-id="e278f-119">Here are a few recommendations for keeping your organization as secure as possible.</span></span>
  
- <span data-ttu-id="e278f-120">Не увеличивайте минимальную длину паролей (8 символов). Больше не значит лучше.</span><span class="sxs-lookup"><span data-stu-id="e278f-120">Maintain an 8-character minimum length requirement (longer isn't necessarily better)</span></span>

- <span data-ttu-id="e278f-121">Don't require character composition requirements.</span><span class="sxs-lookup"><span data-stu-id="e278f-121">Don't require character composition requirements.</span></span> <span data-ttu-id="e278f-122">For example, \*&amp;(^%$</span><span class="sxs-lookup"><span data-stu-id="e278f-122">For example, \*&amp;(^%$</span></span>

- <span data-ttu-id="e278f-123">Не требуйте регулярной смены паролей для учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="e278f-123">Don't require mandatory periodic password resets for user accounts</span></span>

- <span data-ttu-id="e278f-124">Запретите использовать распространенные пароли, чтобы в системе не было самых уязвимых паролей.</span><span class="sxs-lookup"><span data-stu-id="e278f-124">Ban common passwords, to keep the most vulnerable passwords out of your system</span></span>

- <span data-ttu-id="e278f-125">Попросите сотрудников не использовать пароли от рабочих учебных записей для личных целей.</span><span class="sxs-lookup"><span data-stu-id="e278f-125">Educate your users to not re-use their organization passwords for non-work related purposes</span></span>

- <span data-ttu-id="e278f-126">Потребуйте использования [многофакторной проверки подлинности](../security-and-compliance/set-up-multi-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="e278f-126">Enforce registration for [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md)</span></span>

- <span data-ttu-id="e278f-127">Включите запросы многофакторной проверки подлинности с учетом рисков.</span><span class="sxs-lookup"><span data-stu-id="e278f-127">Enable risk-based multi-factor authentication challenges</span></span>

### <a name="password-guidance-for-your-users"></a><span data-ttu-id="e278f-128">Рекомендации для пользователей по выбору паролей</span><span class="sxs-lookup"><span data-stu-id="e278f-128">Password guidance for your users</span></span>

<span data-ttu-id="e278f-129">Here's some password guidance for users in your organization.</span><span class="sxs-lookup"><span data-stu-id="e278f-129">Here's some password guidance for users in your organization.</span></span> <span data-ttu-id="e278f-130">Make sure to let your users know about these recommendations and enforce the recommended password policies at the organizational level.</span><span class="sxs-lookup"><span data-stu-id="e278f-130">Make sure to let your users know about these recommendations and enforce the recommended password policies at the organizational level.</span></span>
  
- <span data-ttu-id="e278f-131">Не используйте такие же пароли, как на других сайтах, или аналогичные им.</span><span class="sxs-lookup"><span data-stu-id="e278f-131">Don't use a password that is the same or similar to one you use on any other websites</span></span>

- <span data-ttu-id="e278f-132">Не используйте в качестве пароля одно слово, например **password**, или частые фразы, например **Iloveyou**.</span><span class="sxs-lookup"><span data-stu-id="e278f-132">Don't use a single word, for example, **password**, or a commonly-used phrase like **Iloveyou**</span></span>

- <span data-ttu-id="e278f-133">Используйте пароли, которые будет сложно угадать даже тем, кто хорошо вас знает. Не включайте в них имена и дни рождения своих родных и друзей, названия любимых групп или фразы, которые вы часто произносите.</span><span class="sxs-lookup"><span data-stu-id="e278f-133">Make passwords hard to guess, even by those who know a lot about you, such as the names and birthdays of your friends and family, your favorite bands, and phrases you like to use</span></span>

## <a name="some-common-approaches-and-their-negative-impacts"></a><span data-ttu-id="e278f-134">Распространенные требования к паролям и их негативное влияние</span><span class="sxs-lookup"><span data-stu-id="e278f-134">Some common approaches and their negative impacts</span></span>

<span data-ttu-id="e278f-135">Описанные ниже принципы управления паролями часто используются в компаниях, но, согласно исследованиям, это зачастую приводит к отрицательным последствиям.</span><span class="sxs-lookup"><span data-stu-id="e278f-135">These are some of the most commonly used password management practices, but research warns us about the negative impacts of them.</span></span>
  
### <a name="password-expiration-requirements-for-users"></a><span data-ttu-id="e278f-136">Требования к окончанию срока действия паролей</span><span class="sxs-lookup"><span data-stu-id="e278f-136">Password expiration requirements for users</span></span>

<span data-ttu-id="e278f-137">Password expiration requirements do more harm than good, because these requirements make users select predictable passwords, composed of sequential words and numbers which are closely related to each other.</span><span class="sxs-lookup"><span data-stu-id="e278f-137">Password expiration requirements do more harm than good, because these requirements make users select predictable passwords, composed of sequential words and numbers which are closely related to each other.</span></span> <span data-ttu-id="e278f-138">In these cases, the next password can be predicted based on the previous password.</span><span class="sxs-lookup"><span data-stu-id="e278f-138">In these cases, the next password can be predicted based on the previous password.</span></span> <span data-ttu-id="e278f-139">Password expiration requirements offer no containment benefits because cyber criminals almost always use credentials as soon as they compromise them.</span><span class="sxs-lookup"><span data-stu-id="e278f-139">Password expiration requirements offer no containment benefits because cyber criminals almost always use credentials as soon as they compromise them.</span></span>
  
### <a name="requiring-long-passwords"></a><span data-ttu-id="e278f-140">Требование длинных паролей</span><span class="sxs-lookup"><span data-stu-id="e278f-140">Requiring long passwords</span></span>

<span data-ttu-id="e278f-141">Password length requirements (greater than about 10 characters) can result in user behavior that is predictable and undesirable.</span><span class="sxs-lookup"><span data-stu-id="e278f-141">Password length requirements (greater than about 10 characters) can result in user behavior that is predictable and undesirable.</span></span> <span data-ttu-id="e278f-142">For example, users who are required to have a 16-character password may choose repeating patterns like **fourfourfourfour** or **passwordpassword** that meet the character length requirement but aren't hard to guess.</span><span class="sxs-lookup"><span data-stu-id="e278f-142">For example, users who are required to have a 16-character password may choose repeating patterns like **fourfourfourfour** or **passwordpassword** that meet the character length requirement but aren't hard to guess.</span></span> <span data-ttu-id="e278f-143">Additionally, length requirements increase the chances that users will adopt other insecure practices, such as writing their passwords down, re-using them, or storing them unencrypted in their documents.</span><span class="sxs-lookup"><span data-stu-id="e278f-143">Additionally, length requirements increase the chances that users will adopt other insecure practices, such as writing their passwords down, re-using them, or storing them unencrypted in their documents.</span></span> <span data-ttu-id="e278f-144">To encourage users to think about a unique password, we recommend keeping a reasonable 8-character minimum length requirement.</span><span class="sxs-lookup"><span data-stu-id="e278f-144">To encourage users to think about a unique password, we recommend keeping a reasonable 8-character minimum length requirement.</span></span> 
  
### <a name="requiring-the-use-of-multiple-character-sets"></a><span data-ttu-id="e278f-145">Требование использования нескольких типов символов</span><span class="sxs-lookup"><span data-stu-id="e278f-145">Requiring the use of multiple character sets</span></span>

<span data-ttu-id="e278f-146">Password complexity requirements reduce key space and cause users to act in predictable ways, doing more harm than good.</span><span class="sxs-lookup"><span data-stu-id="e278f-146">Password complexity requirements reduce key space and cause users to act in predictable ways, doing more harm than good.</span></span> <span data-ttu-id="e278f-147">Most systems enforce some level of password complexity requirements.</span><span class="sxs-lookup"><span data-stu-id="e278f-147">Most systems enforce some level of password complexity requirements.</span></span> <span data-ttu-id="e278f-148">For example, passwords need characters from all three of the following categories:</span><span class="sxs-lookup"><span data-stu-id="e278f-148">For example, passwords need characters from all three of the following categories:</span></span>
  
- <span data-ttu-id="e278f-149">прописные буквы;</span><span class="sxs-lookup"><span data-stu-id="e278f-149">uppercase characters</span></span>

- <span data-ttu-id="e278f-150">строчные буквы;</span><span class="sxs-lookup"><span data-stu-id="e278f-150">lowercase characters</span></span>

- <span data-ttu-id="e278f-151">небуквенные символы.</span><span class="sxs-lookup"><span data-stu-id="e278f-151">non-alphanumeric characters</span></span>

<span data-ttu-id="e278f-152">Most people use similar patterns, for example, a capital letter in the first position, a symbol in the last, and a number in the last 2.</span><span class="sxs-lookup"><span data-stu-id="e278f-152">Most people use similar patterns, for example, a capital letter in the first position, a symbol in the last, and a number in the last 2.</span></span> <span data-ttu-id="e278f-153">Cyber criminals know this, so they run their dictionary attacks using the most common substitutions, "$" for "s", "@" for "a," "1" for "l".</span><span class="sxs-lookup"><span data-stu-id="e278f-153">Cyber criminals know this, so they run their dictionary attacks using the most common substitutions, "$" for "s", "@" for "a," "1" for "l".</span></span> <span data-ttu-id="e278f-154">Forcing your users to choose a combination of upper, lower, digits, special characters has a negative effect.</span><span class="sxs-lookup"><span data-stu-id="e278f-154">Forcing your users to choose a combination of upper, lower, digits, special characters has a negative effect.</span></span> <span data-ttu-id="e278f-155">Some complexity requirements even prevent users from using secure and memorable passwords, and force them into coming up with less secure and less memorable passwords.</span><span class="sxs-lookup"><span data-stu-id="e278f-155">Some complexity requirements even prevent users from using secure and memorable passwords, and force them into coming up with less secure and less memorable passwords.</span></span>
  
## <a name="successful-patterns"></a><span data-ttu-id="e278f-156">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="e278f-156">Successful Patterns</span></span>

<span data-ttu-id="e278f-157">Ниже приведены некоторые рекомендации, которые помогут обеспечить разнообразие паролей.</span><span class="sxs-lookup"><span data-stu-id="e278f-157">In contrast, here are some recommendations in encouraging password diversity.</span></span>
  
### <a name="ban-common-passwords"></a><span data-ttu-id="e278f-158">Запретите распространенные пароли</span><span class="sxs-lookup"><span data-stu-id="e278f-158">Ban common passwords</span></span>

<span data-ttu-id="e278f-159">The most important password requirement you should put on your users when creating passwords is to ban the use of common passwords to reduce your organization's susceptibility to brute force password attacks.</span><span class="sxs-lookup"><span data-stu-id="e278f-159">The most important password requirement you should put on your users when creating passwords is to ban the use of common passwords to reduce your organization's susceptibility to brute force password attacks.</span></span> <span data-ttu-id="e278f-160">Common user passwords include, **abdcefg**, **password**, **monkey**.</span><span class="sxs-lookup"><span data-stu-id="e278f-160">Common user passwords include, **abdcefg**, **password**, **monkey**.</span></span>
  
### <a name="educate-users-to-not-re-use-organization-passwords-anywhere-else"></a><span data-ttu-id="e278f-161">Попросите сотрудников не использовать пароли организации для других целей</span><span class="sxs-lookup"><span data-stu-id="e278f-161">Educate users to not re-use organization passwords anywhere else</span></span>

<span data-ttu-id="e278f-162">One of the most important messages to get across to users in your organization is to not re-use their organization password anywhere else.</span><span class="sxs-lookup"><span data-stu-id="e278f-162">One of the most important messages to get across to users in your organization is to not re-use their organization password anywhere else.</span></span> <span data-ttu-id="e278f-163">The use of organization passwords in external websites greatly increases the likelihood that cyber criminals will compromise these passwords.</span><span class="sxs-lookup"><span data-stu-id="e278f-163">The use of organization passwords in external websites greatly increases the likelihood that cyber criminals will compromise these passwords.</span></span>
  
### <a name="enforce-multi-factor-authentication-registration"></a><span data-ttu-id="e278f-164">Принудительно применяйте многофакторную проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="e278f-164">Enforce Multi-Factor Authentication registration</span></span>

<span data-ttu-id="e278f-165">Make sure your users update contact and security information, like an alternate email address, phone number, or a device registered for push notifications, so they can respond to security challenges and be notified of security events.</span><span class="sxs-lookup"><span data-stu-id="e278f-165">Make sure your users update contact and security information, like an alternate email address, phone number, or a device registered for push notifications, so they can respond to security challenges and be notified of security events.</span></span> <span data-ttu-id="e278f-166">Updated contact and security information helps users verify their identity if they ever forget their password, or if someone else tries to take over their account.</span><span class="sxs-lookup"><span data-stu-id="e278f-166">Updated contact and security information helps users verify their identity if they ever forget their password, or if someone else tries to take over their account.</span></span> <span data-ttu-id="e278f-167">It also provides an out of band notification channel in the case of security events such as login attempts or changed passwords.</span><span class="sxs-lookup"><span data-stu-id="e278f-167">It also provides an out of band notification channel in the case of security events such as login attempts or changed passwords.</span></span> 
  
<span data-ttu-id="e278f-168">Дополнительные сведения см. в статье [Настройка многофакторной проверки подлинности](../security-and-compliance/set-up-multi-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="e278f-168">To learn more, see [Set up multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>
  
### <a name="enable-risk-based-multi-factor-authentication"></a><span data-ttu-id="e278f-169">Включите многофакторную проверку подлинности с учетом рисков</span><span class="sxs-lookup"><span data-stu-id="e278f-169">Enable risk-based multi-factor authentication</span></span>

<span data-ttu-id="e278f-170">Многофакторная проверка подлинности с учетом рисков гарантирует, что если наша система обнаружит подозрительную активность, она выведет запрос, позволяющий убедиться, что действия выполнены владельцем учетной записи.</span><span class="sxs-lookup"><span data-stu-id="e278f-170">Risk-based multi-factor authentication ensures that when our system detects suspicious activity, it can challenge the user to ensure that they are the legitimate account owner.</span></span> 
  
## <a name="want-to-know-more-recommended-reading"></a><span data-ttu-id="e278f-171">Хотите узнать больше?</span><span class="sxs-lookup"><span data-stu-id="e278f-171">Want to know more?</span></span> <span data-ttu-id="e278f-172">Рекомендуемая литература</span><span class="sxs-lookup"><span data-stu-id="e278f-172">Recommended reading</span></span>

- <span data-ttu-id="e278f-173">[К каким результатам приводят надежные пароли?](https://go.microsoft.com/fwlink/p/?linkid=861008) (на английском языке)</span><span class="sxs-lookup"><span data-stu-id="e278f-173">[Do Strong Web Passwords Accomplish Anything?](https://go.microsoft.com/fwlink/p/?linkid=861008)</span></span>

- <span data-ttu-id="e278f-174">[Портфолио паролей и пользователь с ограниченными усилиями](https://go.microsoft.com/fwlink/p/?linkid=861014) (на английском языке)</span><span class="sxs-lookup"><span data-stu-id="e278f-174">[Password Portfolios and the Finite-Effort User](https://go.microsoft.com/fwlink/p/?linkid=861014)</span></span>

- <span data-ttu-id="e278f-175">[Предотвращение ненадежных паролей путем прогнозирования действий пользователей](https://go.microsoft.com/fwlink/p/?linkid=861015) (на английском языке)</span><span class="sxs-lookup"><span data-stu-id="e278f-175">[Preventing Weak Passwords by Reading Users' Minds](https://go.microsoft.com/fwlink/p/?linkid=861015)</span></span>

- <span data-ttu-id="e278f-176">[Выбор безопасных паролей](https://go.microsoft.com/fwlink/p/?linkid=861016) (на английском языке)</span><span class="sxs-lookup"><span data-stu-id="e278f-176">[Choosing Secure Passwords](https://go.microsoft.com/fwlink/p/?linkid=861016)</span></span>

- <span data-ttu-id="e278f-177">[Пора отказаться от обязательной смены паролей](https://go.microsoft.com/fwlink/p/?linkid=861018) (на английском языке)</span><span class="sxs-lookup"><span data-stu-id="e278f-177">[Time to rethink mandatory password changes](https://go.microsoft.com/fwlink/p/?linkid=861018)</span></span>

- <span data-ttu-id="e278f-178">[Худшие пароли 2015 г.](https://go.microsoft.com/fwlink/p/?linkid=861020) (на английском языке)</span><span class="sxs-lookup"><span data-stu-id="e278f-178">[Worst Passwords of 2015](https://go.microsoft.com/fwlink/p/?linkid=861020)</span></span>

- [<span data-ttu-id="e278f-179">Скачивание файлов из Интернета</span><span class="sxs-lookup"><span data-stu-id="e278f-179">Download files from the web</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861029)

## <a name="related-articles"></a><span data-ttu-id="e278f-180">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="e278f-180">Related articles</span></span>

[<span data-ttu-id="e278f-181">Сброс паролей</span><span class="sxs-lookup"><span data-stu-id="e278f-181">Reset passwords</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/reset-passwords)

[<span data-ttu-id="e278f-182">Установка бессрочных пользовательских паролей</span><span class="sxs-lookup"><span data-stu-id="e278f-182">Set an individual user's password to never expire</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/set-password-to-never-expire)

[<span data-ttu-id="e278f-183">Предоставление пользователям прав на самостоятельный сброс пароля</span><span class="sxs-lookup"><span data-stu-id="e278f-183">Let users reset their own passwords</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/let-users-reset-passwords)

[<span data-ttu-id="e278f-184">Повторная отправка пароля пользователя. Справка для администраторов</span><span class="sxs-lookup"><span data-stu-id="e278f-184">Resend a user's password - Admin Help</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/resend-user-password)
