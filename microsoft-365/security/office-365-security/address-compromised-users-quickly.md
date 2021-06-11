---
title: Адрес скомпрометировать учетные записи пользователей с помощью автоматического расследования и ответа
keywords: AIR, autoIR, Microsoft Defender for Endpoint, automated, investigation, response, remediation, threats, advanced, threat, protection, compromised
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
ms.date: 06/10/2021
description: Узнайте, как ускорить процесс обнаружения и устранения скомпрометизированных учетных записей пользователей с помощью автоматизированных возможностей расследования и ответа в Microsoft Defender для Office 365 Plan 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cd84617230e774b92902ef3d11a365c1965ac814
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904144"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a><span data-ttu-id="640c8-104">Адрес скомпрометировать учетные записи пользователей с помощью автоматического расследования и ответа</span><span class="sxs-lookup"><span data-stu-id="640c8-104">Address compromised user accounts with automated investigation and response</span></span>

<span data-ttu-id="640c8-105">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="640c8-105">**Applies to**</span></span>
- [<span data-ttu-id="640c8-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="640c8-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="640c8-107">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="640c8-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="640c8-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="640c8-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)


<span data-ttu-id="640c8-109">[Microsoft Defender для Office 365 Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) включает в себя мощные возможности автоматического расследования [и](office-365-air.md) ответа (AIR).</span><span class="sxs-lookup"><span data-stu-id="640c8-109">[Microsoft Defender for Office 365 Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) includes powerful [automated investigation and response](office-365-air.md) (AIR) capabilities.</span></span> <span data-ttu-id="640c8-110">Такие возможности могут сэкономить группе операций безопасности много времени и усилий, чтобы справиться с угрозами.</span><span class="sxs-lookup"><span data-stu-id="640c8-110">Such capabilities can save your security operations team a lot of time and effort dealing with threats.</span></span> <span data-ttu-id="640c8-111">Корпорация Майкрософт продолжает улучшать возможности безопасности.</span><span class="sxs-lookup"><span data-stu-id="640c8-111">Microsoft continues to improve security capabilities.</span></span> <span data-ttu-id="640c8-112">Недавно возможности AIR были расширены, чтобы включить скомпрометированную книгу безопасности пользователей (в настоящее время в предварительном просмотре).</span><span class="sxs-lookup"><span data-stu-id="640c8-112">Recently, AIR capabilities were enhanced to include a compromised user security playbook (currently in preview).</span></span> <span data-ttu-id="640c8-113">Ознакомьтесь с этой статьей, чтобы узнать больше о скомпрометированной книге безопасности пользователей.</span><span class="sxs-lookup"><span data-stu-id="640c8-113">Read this article to learn more about the compromised user security playbook.</span></span> <span data-ttu-id="640c8-114">Дополнительные сведения см. в записи блога Speed [up time to detect and respond to user compromise and limit breach scope with Microsoft Defender for Office 365.](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053)</span><span class="sxs-lookup"><span data-stu-id="640c8-114">And see the blog post [Speed up time to detect and respond to user compromise and limit breach scope with Microsoft Defender for Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) for additional details.</span></span>

![Автоматическое расследование для скомпрометированного пользователя](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

<span data-ttu-id="640c8-116">Скомпрометированная книга безопасности пользователей позволяет группе безопасности вашей организации:</span><span class="sxs-lookup"><span data-stu-id="640c8-116">The compromised user security playbook enables your organization's security team to:</span></span>

- <span data-ttu-id="640c8-117">Ускорение обнаружения скомпрометированных учетных записей пользователей;</span><span class="sxs-lookup"><span data-stu-id="640c8-117">Speed up detection of compromised user accounts;</span></span>

- <span data-ttu-id="640c8-118">Ограничение масштабов нарушения при взломе учетной записи; и</span><span class="sxs-lookup"><span data-stu-id="640c8-118">Limit the scope of a breach when an account is compromised; and</span></span>

- <span data-ttu-id="640c8-119">Реагировать на скомпрометированную пользователей более эффективно и эффективно.</span><span class="sxs-lookup"><span data-stu-id="640c8-119">Respond to compromised users more effectively and efficiently.</span></span>

## <a name="compromised-user-alerts"></a><span data-ttu-id="640c8-120">Скомпрометированная оповещений пользователей</span><span class="sxs-lookup"><span data-stu-id="640c8-120">Compromised user alerts</span></span>

<span data-ttu-id="640c8-121">При взломе учетной записи пользователя возникают нетипичные или аномальные действия.</span><span class="sxs-lookup"><span data-stu-id="640c8-121">When a user account is compromised, atypical or anomalous behaviors occur.</span></span> <span data-ttu-id="640c8-122">Например, фишинговые и спам-сообщения могут отправляться внутренне из доверенного учетного записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="640c8-122">For example, phishing and spam messages might be sent internally from a trusted user account.</span></span> <span data-ttu-id="640c8-123">Защитник для Office 365 может обнаруживать такие аномалии в шаблонах электронной почты и совместной деятельности в Office 365.</span><span class="sxs-lookup"><span data-stu-id="640c8-123">Defender for Office 365 can detect such anomalies in email patterns and collaboration activity within Office 365.</span></span> <span data-ttu-id="640c8-124">Когда это произойдет, срабатывает оповещение и начинается процесс смягчения угрозы.</span><span class="sxs-lookup"><span data-stu-id="640c8-124">When this happens, alerts are triggered, and the threat mitigation process begins.</span></span>

<span data-ttu-id="640c8-125">Например, вот предупреждение, которое было вызвано из-за подозрительной отправки электронной почты:</span><span class="sxs-lookup"><span data-stu-id="640c8-125">For example, here's an alert that was triggered because of suspicious email sending:</span></span>

![Предупреждение, срабатывает из-за подозрительной отправки электронной почты](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

<span data-ttu-id="640c8-127">И вот пример оповещения, срабатываемого при ограничении отправки для пользователя:</span><span class="sxs-lookup"><span data-stu-id="640c8-127">And here's an example of an alert that was triggered when a sending limit was reached for a user:</span></span>

![Оповещение, срабатыв с помощью ограничения отправки](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a><span data-ttu-id="640c8-129">Исследование и реагирование на скомпрометированного пользователя</span><span class="sxs-lookup"><span data-stu-id="640c8-129">Investigate and respond to a compromised user</span></span>

<span data-ttu-id="640c8-130">При взломе учетной записи пользователя срабатывает оповещение.</span><span class="sxs-lookup"><span data-stu-id="640c8-130">When a user account is compromised, alerts are triggered.</span></span> <span data-ttu-id="640c8-131">В некоторых случаях эта учетная запись пользователя блокируется и не может отправлять дополнительные сообщения электронной почты до тех пор, пока проблема не будет устранена командой операций безопасности организации.</span><span class="sxs-lookup"><span data-stu-id="640c8-131">And in some cases, that user account is blocked and prevented from sending any further email messages until the issue is resolved by your organization's security operations team.</span></span> <span data-ttu-id="640c8-132">В других случаях начинается автоматическое расследование, которое может привести к рекомендуемые действия, которые должна принять ваша группа безопасности.</span><span class="sxs-lookup"><span data-stu-id="640c8-132">In other cases, an automated investigation begins which can result in recommended actions that your security team should take.</span></span>

- [<span data-ttu-id="640c8-133">Просмотр и исследование пользователей с ограниченным доступом</span><span class="sxs-lookup"><span data-stu-id="640c8-133">View and investigate restricted users</span></span>](#view-and-investigate-restricted-users)

- [<span data-ttu-id="640c8-134">Просмотр сведений об автоматизированных расследованиях</span><span class="sxs-lookup"><span data-stu-id="640c8-134">View details about automated investigations</span></span>](#view-details-about-automated-investigations)

> [!IMPORTANT]
> <span data-ttu-id="640c8-135">Для выполнения следующих задач необходимо иметь соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="640c8-135">You must have appropriate permissions to perform the following tasks.</span></span> <span data-ttu-id="640c8-136">См. [необходимые разрешения на использование возможностей AIR.](office-365-air.md#required-permissions-to-use-air-capabilities)</span><span class="sxs-lookup"><span data-stu-id="640c8-136">See [Required permissions to use AIR capabilities](office-365-air.md#required-permissions-to-use-air-capabilities).</span></span>

### <a name="view-and-investigate-restricted-users"></a><span data-ttu-id="640c8-137">Просмотр и исследование пользователей с ограниченным доступом</span><span class="sxs-lookup"><span data-stu-id="640c8-137">View and investigate restricted users</span></span>

<span data-ttu-id="640c8-138">У вас есть несколько вариантов для навигации по списку ограниченных пользователей.</span><span class="sxs-lookup"><span data-stu-id="640c8-138">You have a few options for navigating to a list of restricted users.</span></span> <span data-ttu-id="640c8-139">Например, в Центре & безопасности можно перейти в **Службу** управления угрозами \> **с** \> **ограниченными пользователями.**</span><span class="sxs-lookup"><span data-stu-id="640c8-139">For example, in the Security & Compliance Center, you can go to **Threat management** \> **Review** \> **Restricted Users**.</span></span> <span data-ttu-id="640c8-140">В следующей процедуре  описывается навигация с помощью панели оповещений, которая является хорошим способом для наблюдения за различными видами оповещений, которые могли быть срабатывания.</span><span class="sxs-lookup"><span data-stu-id="640c8-140">The following procedure describes navigation using the **Alerts** dashboard, which is a good way to see various kinds of alerts that might have been triggered.</span></span>

1. <span data-ttu-id="640c8-141">Перейдите на страницу [https://protection.office.com](https://protection.office.com) и войдите.</span><span class="sxs-lookup"><span data-stu-id="640c8-141">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span>

2. <span data-ttu-id="640c8-142">В области навигации выберите панель **оповещений** \> .</span><span class="sxs-lookup"><span data-stu-id="640c8-142">In the navigation pane, choose **Alerts** \> **Dashboard**.</span></span>

3. <span data-ttu-id="640c8-143">В **виджете Другие оповещения** выберите **ограниченных пользователей**.</span><span class="sxs-lookup"><span data-stu-id="640c8-143">In the **Other alerts** widget, choose **Restricted Users**.</span></span>

   ![Другие виджеты оповещений](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   <span data-ttu-id="640c8-145">Это открывает список пользователей с ограниченным доступом.</span><span class="sxs-lookup"><span data-stu-id="640c8-145">This opens the list of restricted users.</span></span>

   ![Ограниченные пользователи в Office 365](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. <span data-ttu-id="640c8-147">Выберите учетную запись пользователя в списке для просмотра сведений и принятия действий, например освобождения [пользователя с ограниченным доступом.](removing-user-from-restricted-users-portal-after-spam.md)</span><span class="sxs-lookup"><span data-stu-id="640c8-147">Select a user account in the list to view details and take action, such as [releasing the restricted user](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

### <a name="view-details-about-automated-investigations"></a><span data-ttu-id="640c8-148">Просмотр сведений об автоматизированных расследованиях</span><span class="sxs-lookup"><span data-stu-id="640c8-148">View details about automated investigations</span></span>

<span data-ttu-id="640c8-149">После начала автоматического расследования вы можете увидеть его сведения и результаты в Центре & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="640c8-149">When an automated investigation has begun, you can see its details and results in the Security & Compliance Center.</span></span> <span data-ttu-id="640c8-150">Перейдите **к исследованиям** управления \> **угрозами,** а затем выберите исследование, чтобы просмотреть его сведения.</span><span class="sxs-lookup"><span data-stu-id="640c8-150">Go to **Threat management** \> **Investigations**, and then select an investigation to view its details.</span></span>

<span data-ttu-id="640c8-151">Дополнительные сведения [см. в материале Просмотр сведений о расследовании.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="640c8-151">To learn more, see [View details of an investigation](air-view-investigation-results.md).</span></span>

## <a name="keep-the-following-points-in-mind"></a><span data-ttu-id="640c8-152">Имейте в виду следующие точки</span><span class="sxs-lookup"><span data-stu-id="640c8-152">Keep the following points in mind</span></span>

- <span data-ttu-id="640c8-153">**Оставайтесь на вершине оповещений.**</span><span class="sxs-lookup"><span data-stu-id="640c8-153">**Stay on top of your alerts**.</span></span> <span data-ttu-id="640c8-154">Как известно, чем дольше компромисс не будет найден, тем больше вероятность широкого воздействия и затрат для организации, клиентов и партнеров.</span><span class="sxs-lookup"><span data-stu-id="640c8-154">As you know, the longer a compromise goes undetected, the larger the potential for widespread impact and cost to your organization, customers, and partners.</span></span> <span data-ttu-id="640c8-155">Раннее обнаружение и своевременное реагирование имеют решающее значение для смягчения угроз, особенно при взломе учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="640c8-155">Early detection and timely response are critical to mitigate threats, and especially when a user's account is compromised.</span></span>

- <span data-ttu-id="640c8-156">**Автоматизация помогает, но не заменяет команду** операций безопасности.</span><span class="sxs-lookup"><span data-stu-id="640c8-156">**Automation assists, but does not replace, your security operations team**.</span></span> <span data-ttu-id="640c8-157">Возможности автоматического расследования и реагирования могут обнаруживать скомпрометированного пользователя на ранних стадиях, но вашей группе операций безопасности, скорее всего, потребуется привлечь и сделать некоторое исследование и исправление.</span><span class="sxs-lookup"><span data-stu-id="640c8-157">Automated investigation and response capabilities can detect a compromised user early on, but your security operations team will likely need to engage and do some investigation and remediation.</span></span> <span data-ttu-id="640c8-158">Нужна помощь в этом?</span><span class="sxs-lookup"><span data-stu-id="640c8-158">Need some help with this?</span></span> <span data-ttu-id="640c8-159">См. [обзор и утверждение действий.](air-review-approve-pending-completed-actions.md)</span><span class="sxs-lookup"><span data-stu-id="640c8-159">See [Review and approve actions](air-review-approve-pending-completed-actions.md).</span></span>

- <span data-ttu-id="640c8-160">**Не полагаться на подозрительное оповещение входа как единственный индикатор**.</span><span class="sxs-lookup"><span data-stu-id="640c8-160">**Don't rely on a suspicious login alert as your only indicator**.</span></span> <span data-ttu-id="640c8-161">Если учетная запись пользователя скомпрометирована, она может вызвать или не вызвать подозрительное оповещение о входе.</span><span class="sxs-lookup"><span data-stu-id="640c8-161">When a user account is compromised, it might or might not trigger a suspicious login alert.</span></span> <span data-ttu-id="640c8-162">Иногда это серия действий, которые происходят после взлома учетной записи, которая вызывает оповещение.</span><span class="sxs-lookup"><span data-stu-id="640c8-162">Sometimes it's the series of activities that occur after an account is compromised that triggers an alert.</span></span> <span data-ttu-id="640c8-163">Хотите узнать больше о оповещениях?</span><span class="sxs-lookup"><span data-stu-id="640c8-163">Want to know more about alerts?</span></span> <span data-ttu-id="640c8-164">См. [политики оповещения.](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="640c8-164">See [Alert policies](../../compliance/alert-policies.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="640c8-165">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="640c8-165">Next steps</span></span>

- [<span data-ttu-id="640c8-166">Просмотр необходимых разрешений для использования возможностей AIR</span><span class="sxs-lookup"><span data-stu-id="640c8-166">Review the required permissions to use AIR capabilities</span></span>](office-365-air.md#required-permissions-to-use-air-capabilities)

- [<span data-ttu-id="640c8-167">Поиск и расследование вредоносной электронной почты в Office 365</span><span class="sxs-lookup"><span data-stu-id="640c8-167">Find and investigate malicious email in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)

- [<span data-ttu-id="640c8-168">Узнайте о AIR в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="640c8-168">Learn about AIR in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="640c8-169">Посетите дорожную карту Microsoft 365, чтобы узнать, что будет в ближайшее время, и выйти</span><span class="sxs-lookup"><span data-stu-id="640c8-169">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)