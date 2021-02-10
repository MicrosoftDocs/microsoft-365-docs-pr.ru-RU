---
title: Устранение компрометации учетных записей пользователей с помощью автоматического исследования и реагирования
keywords: AIR, autoIR, ATP, автоматизированный, исследование, ответ, исправление, угрозы, расширенные, угроза, защита, скомпрометирован
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
ms.date: 02/25/2020
description: Узнайте, как ускорить процесс обнаружения и устранения компрометации учетных записей пользователей с помощью автоматизированного исследования и реагирования в Microsoft Defender для Office 365 (план 2).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2159ab7ad7e13c4cd4c2c428317ee7d99f78158c
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "50176067"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a><span data-ttu-id="4b4ba-104">Устранение компрометации учетных записей пользователей с помощью автоматического исследования и реагирования</span><span class="sxs-lookup"><span data-stu-id="4b4ba-104">Address compromised user accounts with automated investigation and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4b4ba-105">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="4b4ba-105">**Applies to**</span></span>
- [<span data-ttu-id="4b4ba-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="4b4ba-106">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="4b4ba-107">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="4b4ba-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="4b4ba-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4b4ba-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="4b4ba-109">[Microsoft Defender для Office 365 (план 2)](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) включает мощные автоматизированные средства исследования и [реагирования](office-365-air.md) на них (AIR).</span><span class="sxs-lookup"><span data-stu-id="4b4ba-109">[Microsoft Defender for Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) includes powerful [automated investigation and response](office-365-air.md) (AIR) capabilities.</span></span> <span data-ttu-id="4b4ba-110">Такие возможности могут сэкономить много времени и усилий для работы с угрозами.</span><span class="sxs-lookup"><span data-stu-id="4b4ba-110">Such capabilities can save your security operations team a lot of time and effort dealing with threats.</span></span> <span data-ttu-id="4b4ba-111">Корпорация Майкрософт продолжает улучшать возможности безопасности.</span><span class="sxs-lookup"><span data-stu-id="4b4ba-111">Microsoft continues to improve security capabilities.</span></span> <span data-ttu-id="4b4ba-112">Недавно возможности AIR были расширены, включив в них скомпрометированную книгу безопасности пользователей (в настоящее время она находится в предварительной версии).</span><span class="sxs-lookup"><span data-stu-id="4b4ba-112">Recently, AIR capabilities were enhanced to include a compromised user security playbook (currently in preview).</span></span> <span data-ttu-id="4b4ba-113">Прочитайте эту статью, чтобы узнать больше о скомпрометированной пользовательской книге безопасности.</span><span class="sxs-lookup"><span data-stu-id="4b4ba-113">Read this article to learn more about the compromised user security playbook.</span></span> <span data-ttu-id="4b4ba-114">Дополнительные сведения см. в записи блога " Ускорение времени обнаружения и реагирования на компрометации пользователей и ограничения области нарушения безопасности с помощью [Microsoft Defender для Office 365".](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053)</span><span class="sxs-lookup"><span data-stu-id="4b4ba-114">And see the blog post [Speed up time to detect and respond to user compromise and limit breach scope with Microsoft Defender for Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) for additional details.</span></span>

![Автоматическое исследование скомпрометированного пользователя](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

<span data-ttu-id="4b4ba-116">Скомпрометированная книга безопасности пользователей позволяет группе безопасности вашей организации:</span><span class="sxs-lookup"><span data-stu-id="4b4ba-116">The compromised user security playbook enables your organization's security team to:</span></span>

- <span data-ttu-id="4b4ba-117">Ускорение обнаружения компрометации учетных записей пользователей;</span><span class="sxs-lookup"><span data-stu-id="4b4ba-117">Speed up detection of compromised user accounts;</span></span>

- <span data-ttu-id="4b4ba-118">Ограничение области нарушения безопасности при компрометации учетной записи; и</span><span class="sxs-lookup"><span data-stu-id="4b4ba-118">Limit the scope of a breach when an account is compromised; and</span></span>

- <span data-ttu-id="4b4ba-119">Реагировать на скомпрометированную информацию о пользователях эффективнее и эффективнее.</span><span class="sxs-lookup"><span data-stu-id="4b4ba-119">Respond to compromised users more effectively and efficiently.</span></span>

## <a name="compromised-user-alerts"></a><span data-ttu-id="4b4ba-120">Компрометации оповещений пользователей</span><span class="sxs-lookup"><span data-stu-id="4b4ba-120">Compromised user alerts</span></span>

<span data-ttu-id="4b4ba-121">Если учетная запись пользователя скомпрометирована, происходит нетипическое или аномальное поведение.</span><span class="sxs-lookup"><span data-stu-id="4b4ba-121">When a user account is compromised, atypical or anomalous behaviors occur.</span></span> <span data-ttu-id="4b4ba-122">Например, фишинговые и нежелательные сообщения могут отправляться из внутренней учетной записи доверенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="4b4ba-122">For example, phishing and spam messages might be sent internally from a trusted user account.</span></span> <span data-ttu-id="4b4ba-123">Защитник Office 365 может обнаруживать такие аномалии в шаблонах электронной почты и действиях совместной работы в Office 365.</span><span class="sxs-lookup"><span data-stu-id="4b4ba-123">Defender for Office 365 can detect such anomalies in email patterns and collaboration activity within Office 365.</span></span> <span data-ttu-id="4b4ba-124">В этом случае срабатывает оповещение, и начинается процесс снижения угрозы.</span><span class="sxs-lookup"><span data-stu-id="4b4ba-124">When this happens, alerts are triggered, and the threat mitigation process begins.</span></span>

<span data-ttu-id="4b4ba-125">Например, вот оповещение, которое было вызвано подозрительной отправкой электронной почты:</span><span class="sxs-lookup"><span data-stu-id="4b4ba-125">For example, here's an alert that was triggered because of suspicious email sending:</span></span>

![Оповещение, срабатывает из-за подозрительной отправки электронной почты](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

<span data-ttu-id="4b4ba-127">А вот пример оповещения, которое было срабатывает при достигнутом ограничении на отправку для пользователя:</span><span class="sxs-lookup"><span data-stu-id="4b4ba-127">And here's an example of an alert that was triggered when a sending limit was reached for a user:</span></span>

![Оповещение, срабатыв по достигнутому ограничению на отправку](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a><span data-ttu-id="4b4ba-129">Исследование скомпрометированного пользователя и реагирование на него</span><span class="sxs-lookup"><span data-stu-id="4b4ba-129">Investigate and respond to a compromised user</span></span>

<span data-ttu-id="4b4ba-130">При компрометации учетной записи пользователя инициются оповещения.</span><span class="sxs-lookup"><span data-stu-id="4b4ba-130">When a user account is compromised, alerts are triggered.</span></span> <span data-ttu-id="4b4ba-131">В некоторых случаях эта учетная запись пользователя блокируется и не может отправлять дополнительные сообщения электронной почты, пока проблема не будет устранена командой операций безопасности вашей организации.</span><span class="sxs-lookup"><span data-stu-id="4b4ba-131">And in some cases, that user account is blocked and prevented from sending any further email messages until the issue is resolved by your organization's security operations team.</span></span> <span data-ttu-id="4b4ba-132">В других случаях начинается автоматизированное исследование, которое может привести к рекомендуемые действия, которые должна принять группа безопасности.</span><span class="sxs-lookup"><span data-stu-id="4b4ba-132">In other cases, an automated investigation begins which can result in recommended actions that your security team should take.</span></span>

- [<span data-ttu-id="4b4ba-133">Просмотр и исследование пользователей с ограниченным доступом</span><span class="sxs-lookup"><span data-stu-id="4b4ba-133">View and investigate restricted users</span></span>](#view-and-investigate-restricted-users)

- [<span data-ttu-id="4b4ba-134">Просмотр сведений об автоматизированных расследованиях</span><span class="sxs-lookup"><span data-stu-id="4b4ba-134">View details about automated investigations</span></span>](#view-details-about-automated-investigations)

> [!IMPORTANT]
> <span data-ttu-id="4b4ba-135">Для выполнения следующих задач необходимы соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="4b4ba-135">You must have appropriate permissions to perform the following tasks.</span></span> <span data-ttu-id="4b4ba-136">См. [необходимые разрешения для использования возможностей AIR.](office-365-air.md#required-permissions-to-use-air-capabilities)</span><span class="sxs-lookup"><span data-stu-id="4b4ba-136">See [Required permissions to use AIR capabilities](office-365-air.md#required-permissions-to-use-air-capabilities).</span></span>

### <a name="view-and-investigate-restricted-users"></a><span data-ttu-id="4b4ba-137">Просмотр и исследование пользователей с ограниченным доступом</span><span class="sxs-lookup"><span data-stu-id="4b4ba-137">View and investigate restricted users</span></span>

<span data-ttu-id="4b4ba-138">У вас есть несколько вариантов для переходов к списку пользователей с ограниченным доступом.</span><span class="sxs-lookup"><span data-stu-id="4b4ba-138">You have a few options for navigating to a list of restricted users.</span></span> <span data-ttu-id="4b4ba-139">Например, в Центре безопасности & соответствия требованиям можно перейти в центр **управления** угрозами \> **"Просмотр** \> **ограниченных пользователей".**</span><span class="sxs-lookup"><span data-stu-id="4b4ba-139">For example, in the Security & Compliance Center, you can go to **Threat management** \> **Review** \> **Restricted Users**.</span></span> <span data-ttu-id="4b4ba-140">В следующей процедуре  описывается навигация с помощью панели мониторинга оповещений, которая является хорошим способом увидеть различные виды оповещений, которые могли быть инициированы.</span><span class="sxs-lookup"><span data-stu-id="4b4ba-140">The following procedure describes navigation using the **Alerts** dashboard, which is a good way to see various kinds of alerts that might have been triggered.</span></span>

1. <span data-ttu-id="4b4ba-141">Перейдите на <https://protection.office.com> и войдите.</span><span class="sxs-lookup"><span data-stu-id="4b4ba-141">Go to <https://protection.office.com> and sign in.</span></span>

2. <span data-ttu-id="4b4ba-142">В области навигации выберите панель **мониторинга оповещений.** \> </span><span class="sxs-lookup"><span data-stu-id="4b4ba-142">In the navigation pane, choose **Alerts** \> **Dashboard**.</span></span>

3. <span data-ttu-id="4b4ba-143">In the **Other alerts** widget, choose **Restricted Users**.</span><span class="sxs-lookup"><span data-stu-id="4b4ba-143">In the **Other alerts** widget, choose **Restricted Users**.</span></span>

   ![Другие виджеты оповещений](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   <span data-ttu-id="4b4ba-145">Откроется список пользователей с ограниченным доступом.</span><span class="sxs-lookup"><span data-stu-id="4b4ba-145">This opens the list of restricted users.</span></span>

   ![Пользователи с ограниченным доступом в Office 365](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. <span data-ttu-id="4b4ba-147">Выберите учетную запись пользователя в списке, чтобы просмотреть сведения и принять меры, например освободить пользователя с ограниченным [доступом.](removing-user-from-restricted-users-portal-after-spam.md)</span><span class="sxs-lookup"><span data-stu-id="4b4ba-147">Select a user account in the list to view details and take action, such as [releasing the restricted user](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

### <a name="view-details-about-automated-investigations"></a><span data-ttu-id="4b4ba-148">Просмотр сведений об автоматизированных расследованиях</span><span class="sxs-lookup"><span data-stu-id="4b4ba-148">View details about automated investigations</span></span>

<span data-ttu-id="4b4ba-149">Когда начинается автоматизированное исследование, вы можете увидеть его подробные сведения и результаты в Центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="4b4ba-149">When an automated investigation has begun, you can see its details and results in the Security & Compliance Center.</span></span> <span data-ttu-id="4b4ba-150">Перейдите **в статью "Исследования управления** \> **угрозами"** и выберите исследование, чтобы просмотреть его сведения.</span><span class="sxs-lookup"><span data-stu-id="4b4ba-150">Go to **Threat management** \> **Investigations**, and then select an investigation to view its details.</span></span>

<span data-ttu-id="4b4ba-151">Дополнительные сведения [см. в сведениях об исследованиях.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="4b4ba-151">To learn more, see [View details of an investigation](air-view-investigation-results.md).</span></span>

## <a name="keep-the-following-points-in-mind"></a><span data-ttu-id="4b4ba-152">Помните о следующих моментах</span><span class="sxs-lookup"><span data-stu-id="4b4ba-152">Keep the following points in mind</span></span>

- <span data-ttu-id="4b4ba-153">**Оставайтесь в верхней части оповещений**.</span><span class="sxs-lookup"><span data-stu-id="4b4ba-153">**Stay on top of your alerts**.</span></span> <span data-ttu-id="4b4ba-154">Как вы знаете, чем дольше компрометация не будет найдена, тем больше вероятность широкого влияния и затрат на вашу организацию, клиентов и партнеров.</span><span class="sxs-lookup"><span data-stu-id="4b4ba-154">As you know, the longer a compromise goes undetected, the larger the potential for widespread impact and cost to your organization, customers, and partners.</span></span> <span data-ttu-id="4b4ba-155">Раннее обнаружение и своевременное реагирование критически важны для снижения угроз, особенно при компрометации учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="4b4ba-155">Early detection and timely response are critical to mitigate threats, and especially when a user's account is compromised.</span></span>

- <span data-ttu-id="4b4ba-156">**Автоматизация помогает, но не заменяет вашу команду** по операциям безопасности.</span><span class="sxs-lookup"><span data-stu-id="4b4ba-156">**Automation assists, but does not replace, your security operations team**.</span></span> <span data-ttu-id="4b4ba-157">Автоматизированные средства исследования и реагирования могут обнаруживать скомпрометированного пользователя на ранних стадиях, но вашей группе по работе с безопасностью, скорее всего, потребуется участвовать в расследовании и исправлении.</span><span class="sxs-lookup"><span data-stu-id="4b4ba-157">Automated investigation and response capabilities can detect a compromised user early on, but your security operations team will likely need to engage and do some investigation and remediation.</span></span> <span data-ttu-id="4b4ba-158">Нужна помощь в этом?</span><span class="sxs-lookup"><span data-stu-id="4b4ba-158">Need some help with this?</span></span> <span data-ttu-id="4b4ba-159">См. ["Проверка и утверждение действий".](air-review-approve-pending-completed-actions.md)</span><span class="sxs-lookup"><span data-stu-id="4b4ba-159">See [Review and approve actions](air-review-approve-pending-completed-actions.md).</span></span>

- <span data-ttu-id="4b4ba-160">**Не полагайтесь на подозрительное** оповещение о входе в систему как единственный индикатор.</span><span class="sxs-lookup"><span data-stu-id="4b4ba-160">**Don't rely on a suspicious login alert as your only indicator**.</span></span> <span data-ttu-id="4b4ba-161">Если учетная запись пользователя скомпрометирована, она может вызывать или не вызывать подозрительное оповещение о входе.</span><span class="sxs-lookup"><span data-stu-id="4b4ba-161">When a user account is compromised, it might or might not trigger a suspicious login alert.</span></span> <span data-ttu-id="4b4ba-162">Иногда оповещение вызывает ряд действий, которые происходят после компрометации учетной записи.</span><span class="sxs-lookup"><span data-stu-id="4b4ba-162">Sometimes it's the series of activities that occur after an account is compromised that triggers an alert.</span></span> <span data-ttu-id="4b4ba-163">Хотите узнать больше об оповещениях?</span><span class="sxs-lookup"><span data-stu-id="4b4ba-163">Want to know more about alerts?</span></span> <span data-ttu-id="4b4ba-164">См. [политики оповещений.](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)</span><span class="sxs-lookup"><span data-stu-id="4b4ba-164">See [Alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).</span></span>

## <a name="next-steps"></a><span data-ttu-id="4b4ba-165">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="4b4ba-165">Next steps</span></span>

- [<span data-ttu-id="4b4ba-166">Просмотр необходимых разрешений для использования возможностей AIR</span><span class="sxs-lookup"><span data-stu-id="4b4ba-166">Review the required permissions to use AIR capabilities</span></span>](office-365-air.md#required-permissions-to-use-air-capabilities)

- [<span data-ttu-id="4b4ba-167">Поиск и изучение вредоносной электронной почты в Office 365</span><span class="sxs-lookup"><span data-stu-id="4b4ba-167">Find and investigate malicious email in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)

- [<span data-ttu-id="4b4ba-168">Узнайте о AIR в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="4b4ba-168">Learn about AIR in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="4b4ba-169">Посетите план развития Microsoft 365, чтобы узнать, что будет в ближайшее время и что будет развертываться</span><span class="sxs-lookup"><span data-stu-id="4b4ba-169">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)
