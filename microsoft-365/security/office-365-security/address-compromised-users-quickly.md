---
title: Устранение скомпрометированных учетных записей пользователей с помощью автоматического исследования и ответа
keywords: ВОЗДУШный, Аутоир, ATP, автоматизированный, исследование, ответ, исправление, угрозы, усовершенствованный, угроза, защита и скомпрометирован
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
ms.date: 02/25/2020
description: Узнайте, как ускорить процесс обнаружения и адресации скомпрометированных учетных записей пользователей с помощью средств автоматического исследования и реагирования в защитнике Майкрософт для Office 365 (план 2).
ms.openlocfilehash: 0da065bea17796d09de771a767991804afb5335b
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844600"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a><span data-ttu-id="ed915-104">Устранение скомпрометированных учетных записей пользователей с помощью автоматического исследования и ответа</span><span class="sxs-lookup"><span data-stu-id="ed915-104">Address compromised user accounts with automated investigation and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="ed915-105">[Защитник Майкрософт для Office 365 (план 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2) ) включает мощные возможности [автоматического исследования и реагирования](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR).</span><span class="sxs-lookup"><span data-stu-id="ed915-105">[Microsoft Defender for Office 365 Plan 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2) includes powerful [automated investigation and response](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR) capabilities.</span></span> <span data-ttu-id="ed915-106">Такие возможности могут сэкономить множество времени и усилий, связанных с угрозами.</span><span class="sxs-lookup"><span data-stu-id="ed915-106">Such capabilities can save your security operations team a lot of time and effort dealing with threats.</span></span> <span data-ttu-id="ed915-107">Корпорация Майкрософт продолжает совершенствовать возможности обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="ed915-107">Microsoft continues to improve security capabilities.</span></span> <span data-ttu-id="ed915-108">Недавно были улучшены возможности работы с ВОЗДУХом, которые включали скомпрометированный стратегия безопасности (в настоящее время предварительная версия).</span><span class="sxs-lookup"><span data-stu-id="ed915-108">Recently, AIR capabilities were enhanced to include a compromised user security playbook (currently in preview).</span></span> <span data-ttu-id="ed915-109">Прочитайте эту статью, чтобы узнать больше о скомпрометированной безопасности пользователя стратегия.</span><span class="sxs-lookup"><span data-stu-id="ed915-109">Read this article to learn more about the compromised user security playbook.</span></span> <span data-ttu-id="ed915-110">И Узнайте больше о скорости записи в блоге, [чтобы обнаруживать и отвечать за безопасность пользователей и ограничивать область ограниченного действия с помощью защитника Майкрософт для Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="ed915-110">And see the blog post [Speed up time to detect and respond to user compromise and limit breach scope with Microsoft Defender for Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) for additional details.</span></span>

![Автоматическое исследование для скомпрометированного пользователя](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

<span data-ttu-id="ed915-112">Скомпрометированная безопасность пользователей стратегия позволяет группе безопасности Организации:</span><span class="sxs-lookup"><span data-stu-id="ed915-112">The compromised user security playbook enables your organization's security team to:</span></span>

- <span data-ttu-id="ed915-113">Ускорить обнаружение скомпрометированных учетных записей пользователей;</span><span class="sxs-lookup"><span data-stu-id="ed915-113">Speed up detection of compromised user accounts;</span></span>

- <span data-ttu-id="ed915-114">Ограничьте область нарушения при раскрытии учетной записи; с</span><span class="sxs-lookup"><span data-stu-id="ed915-114">Limit the scope of a breach when an account is compromised; and</span></span>

- <span data-ttu-id="ed915-115">Более эффективное и эффективное реагирование на скомпрометированные пользователи.</span><span class="sxs-lookup"><span data-stu-id="ed915-115">Respond to compromised users more effectively and efficiently.</span></span>

## <a name="compromised-user-alerts"></a><span data-ttu-id="ed915-116">Скомпрометированные оповещения пользователей</span><span class="sxs-lookup"><span data-stu-id="ed915-116">Compromised user alerts</span></span>

<span data-ttu-id="ed915-117">Если учетная запись пользователя скомпрометирована, возникают нетипичные или аномальные проблемы.</span><span class="sxs-lookup"><span data-stu-id="ed915-117">When a user account is compromised, atypical or anomalous behaviors occur.</span></span> <span data-ttu-id="ed915-118">Например, сообщения фишинга и спама могут отсылаться внутренним образом из надежной учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="ed915-118">For example, phishing and spam messages might be sent internally from a trusted user account.</span></span> <span data-ttu-id="ed915-119">Защитник для Office 365 может обнаруживать такие аномалии в шаблонах электронной почты и действиях по совместной работе в Office 365.</span><span class="sxs-lookup"><span data-stu-id="ed915-119">Defender for Office 365 can detect such anomalies in email patterns and collaboration activity within Office 365.</span></span> <span data-ttu-id="ed915-120">Когда это происходит, запускаются оповещения и начинается процесс устранения угроз.</span><span class="sxs-lookup"><span data-stu-id="ed915-120">When this happens, alerts are triggered, and the threat mitigation process begins.</span></span>

<span data-ttu-id="ed915-121">Например, Вот предупреждение, которое было запущено из-за подозрительных отправок электронной почты:</span><span class="sxs-lookup"><span data-stu-id="ed915-121">For example, here's an alert that was triggered because of suspicious email sending:</span></span>

![Оповещение инициировано из-за подозрительных отправок электронной почты](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

<span data-ttu-id="ed915-123">А вот пример оповещения, которое было активировано при достижении предельного числа отправок для пользователя:</span><span class="sxs-lookup"><span data-stu-id="ed915-123">And here's an example of an alert that was triggered when a sending limit was reached for a user:</span></span>

![Достигнуто оповещение, вызванное лимитом отправки](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a><span data-ttu-id="ed915-125">Анализ скомпрометированного пользователя и ответ на него</span><span class="sxs-lookup"><span data-stu-id="ed915-125">Investigate and respond to a compromised user</span></span>

<span data-ttu-id="ed915-126">При раскрытии учетной записи пользователя запускаются оповещения.</span><span class="sxs-lookup"><span data-stu-id="ed915-126">When a user account is compromised, alerts are triggered.</span></span> <span data-ttu-id="ed915-127">В некоторых случаях эта учетная запись пользователя блокируется и не может отправлять сообщения электронной почты, пока проблема не будет устранена в группе "операции безопасности" Организации.</span><span class="sxs-lookup"><span data-stu-id="ed915-127">And in some cases, that user account is blocked and prevented from sending any further email messages until the issue is resolved by your organization's security operations team.</span></span> <span data-ttu-id="ed915-128">В других случаях начинается автоматическое исследование, которое может привести к рекомендуемым действиям, которые должна выполнять Группа по обеспечению безопасности.</span><span class="sxs-lookup"><span data-stu-id="ed915-128">In other cases, an automated investigation begins which can result in recommended actions that your security team should take.</span></span>

- [<span data-ttu-id="ed915-129">Просмотр и исследование пользователей с ограниченным доступом</span><span class="sxs-lookup"><span data-stu-id="ed915-129">View and investigate restricted users</span></span>](#view-and-investigate-restricted-users)

- [<span data-ttu-id="ed915-130">Просмотр подробных сведений об автоматическом расследовании</span><span class="sxs-lookup"><span data-stu-id="ed915-130">View details about automated investigations</span></span>](#view-details-about-automated-investigations)

> [!IMPORTANT]
> <span data-ttu-id="ed915-131">Для выполнения следующих задач необходимы соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="ed915-131">You must have appropriate permissions to perform the following tasks.</span></span> <span data-ttu-id="ed915-132">Ознакомьтесь [с разрешениями, необходимыми для использования возможностей Air](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air?view=o365-worldwide#required-permissions-to-use-air-capabilities).</span><span class="sxs-lookup"><span data-stu-id="ed915-132">See [Required permissions to use AIR capabilities](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air?view=o365-worldwide#required-permissions-to-use-air-capabilities).</span></span>

### <a name="view-and-investigate-restricted-users"></a><span data-ttu-id="ed915-133">Просмотр и исследование пользователей с ограниченным доступом</span><span class="sxs-lookup"><span data-stu-id="ed915-133">View and investigate restricted users</span></span>

<span data-ttu-id="ed915-134">Существует несколько вариантов перехода к списку пользователей с ограниченным доступом.</span><span class="sxs-lookup"><span data-stu-id="ed915-134">You have a few options for navigating to a list of restricted users.</span></span> <span data-ttu-id="ed915-135">Например, в центре безопасности & соответствия требованиям вы можете перейти к разделу **Управление угрозами**  >  **Проверка**  >  **пользователей с ограниченными возможностями**.</span><span class="sxs-lookup"><span data-stu-id="ed915-135">For example, in the Security & Compliance Center, you can go to **Threat management** > **Review** > **Restricted Users**.</span></span> <span data-ttu-id="ed915-136">Следующая процедура описывает навигацию с помощью панели мониторинга **оповещения** , которая является хорошим способом просмотра различных типов оповещений, которые могут быть активированы.</span><span class="sxs-lookup"><span data-stu-id="ed915-136">The following procedure describes navigation using the **Alerts** dashboard, which is a good way to see various kinds of alerts that might have been triggered.</span></span>

1. <span data-ttu-id="ed915-137">Перейдите на страницу [https://protection.office.com](https://protection.office.com) и войдите.</span><span class="sxs-lookup"><span data-stu-id="ed915-137">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span>

2. <span data-ttu-id="ed915-138">В области навигации выберите панель мониторинга **оповещений**  >  **Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="ed915-138">In the navigation pane, choose **Alerts** > **Dashboard**.</span></span>

3. <span data-ttu-id="ed915-139">В мини-приложении " **другие оповещения** " выберите пункт **ограниченные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="ed915-139">In the **Other alerts** widget, choose **Restricted Users**.</span></span>

   ![Другое мини-приложение "оповещения"](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   <span data-ttu-id="ed915-141">Откроется список пользователей с ограниченным доступом.</span><span class="sxs-lookup"><span data-stu-id="ed915-141">This opens the list of restricted users.</span></span><br/>![Пользователи с ограниченным доступом в Office 365](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. <span data-ttu-id="ed915-143">Выберите учетную запись пользователя в списке, чтобы просмотреть сведения и выполнить действия, такие как [Снятие ограниченного пользователя](https://docs.microsoft.com/microsoft-365/security/office-365-security/removing-user-from-restricted-users-portal-after-spam).</span><span class="sxs-lookup"><span data-stu-id="ed915-143">Select a user account in the list to view details and take action, such as [releasing the restricted user](https://docs.microsoft.com/microsoft-365/security/office-365-security/removing-user-from-restricted-users-portal-after-spam).</span></span>

### <a name="view-details-about-automated-investigations"></a><span data-ttu-id="ed915-144">Просмотр подробных сведений об автоматическом расследовании</span><span class="sxs-lookup"><span data-stu-id="ed915-144">View details about automated investigations</span></span>

<span data-ttu-id="ed915-145">После начала автоматического исследования вы можете просмотреть его сведения и результаты в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="ed915-145">When an automated investigation has begun, you can see its details and results in the Security & Compliance Center.</span></span> <span data-ttu-id="ed915-146">Перейдите к разделу **Управление угрозами**  >  **Investigations** , а затем выберите расследования, чтобы просмотреть сведения о нем.</span><span class="sxs-lookup"><span data-stu-id="ed915-146">Go to **Threat management** > **Investigations** , and then select an investigation to view its details.</span></span>

<span data-ttu-id="ed915-147">Чтобы узнать больше, ознакомьтесь со статьей [Просмотр сведений о расследовании](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results).</span><span class="sxs-lookup"><span data-stu-id="ed915-147">To learn more, see [View details of an investigation](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results).</span></span>

## <a name="keep-the-following-points-in-mind"></a><span data-ttu-id="ed915-148">Учитывайте следующие моменты</span><span class="sxs-lookup"><span data-stu-id="ed915-148">Keep the following points in mind</span></span>

- <span data-ttu-id="ed915-149">**Следите за поверх ваших оповещений**.</span><span class="sxs-lookup"><span data-stu-id="ed915-149">**Stay on top of your alerts**.</span></span> <span data-ttu-id="ed915-150">Как вы знаете, более длительный компромисс не обнаруживается, что увеличивает потенциал для широкого влияния и стоимости вашей организации, клиентам и партнерам.</span><span class="sxs-lookup"><span data-stu-id="ed915-150">As you know, the longer a compromise goes undetected, the larger the potential for widespread impact and cost to your organization, customers, and partners.</span></span> <span data-ttu-id="ed915-151">Раннее обнаружение и своевременное реагирование критически важны для устранения угроз, особенно при компрометации учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="ed915-151">Early detection and timely response are critical to mitigate threats, and especially when a user's account is compromised.</span></span>

- <span data-ttu-id="ed915-152">**Автоматизация помогает, но не заменяет группу операций по обеспечению безопасности**.</span><span class="sxs-lookup"><span data-stu-id="ed915-152">**Automation assists, but does not replace, your security operations team**.</span></span> <span data-ttu-id="ed915-153">Автоматизированное исследование и возможности реагирования могут обнаруживать скомпрометированного пользователя на ранних стадиях, но группе управления безопасностью, скорее всего, потребуется привлечь и провести исследование и исправление.</span><span class="sxs-lookup"><span data-stu-id="ed915-153">Automated investigation and response capabilities can detect a compromised user early on, but your security operations team will likely need to engage and do some investigation and remediation.</span></span> <span data-ttu-id="ed915-154">Нужна помощь по этой рекомендации?</span><span class="sxs-lookup"><span data-stu-id="ed915-154">Need some help with this?</span></span> <span data-ttu-id="ed915-155">Просмотр [и утверждение действий](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air#review-and-approve-actions).</span><span class="sxs-lookup"><span data-stu-id="ed915-155">See [Review and approve actions](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air#review-and-approve-actions).</span></span>

- <span data-ttu-id="ed915-156">**Не полагайтесь на подозрительное оповещение о входе в систему в качестве единственного индикатора**.</span><span class="sxs-lookup"><span data-stu-id="ed915-156">**Don't rely on a suspicious login alert as your only indicator**.</span></span> <span data-ttu-id="ed915-157">Если учетная запись пользователя скомпрометирована, она может вызывать или не запускать подозрительные оповещения о входе в систему.</span><span class="sxs-lookup"><span data-stu-id="ed915-157">When a user account is compromised, it might or might not trigger a suspicious login alert.</span></span> <span data-ttu-id="ed915-158">Иногда это ряд действий, происходящих после компрометации учетной записи, которая запускает оповещение.</span><span class="sxs-lookup"><span data-stu-id="ed915-158">Sometimes it's the series of activities that occur after an account is compromised that triggers an alert.</span></span> <span data-ttu-id="ed915-159">Хотите узнать больше о оповещениях?</span><span class="sxs-lookup"><span data-stu-id="ed915-159">Want to know more about alerts?</span></span> <span data-ttu-id="ed915-160">Ознакомьтесь с [политиками оповещений](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).</span><span class="sxs-lookup"><span data-stu-id="ed915-160">See [Alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).</span></span>

## <a name="next-steps"></a><span data-ttu-id="ed915-161">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="ed915-161">Next steps</span></span>

- [<span data-ttu-id="ed915-162">Ознакомьтесь с разрешениями, необходимыми для использования возможностей воздуха</span><span class="sxs-lookup"><span data-stu-id="ed915-162">Review the required permissions to use AIR capabilities</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air?view=o365-worldwide#required-permissions-to-use-air-capabilities)

- [<span data-ttu-id="ed915-163">Поиск и исследование вредоносных сообщений электронной почты в Office 365</span><span class="sxs-lookup"><span data-stu-id="ed915-163">Find and investigate malicious email in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered?view=o365-worldwide)

- [<span data-ttu-id="ed915-164">Сведения о AIR в защитнике Майкрософт для конечной точки</span><span class="sxs-lookup"><span data-stu-id="ed915-164">Learn about AIR in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="ed915-165">Посетите план Microsoft 365, чтобы узнать, что скоро ожидается и как выполняется развертывание.</span><span class="sxs-lookup"><span data-stu-id="ed915-165">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)

