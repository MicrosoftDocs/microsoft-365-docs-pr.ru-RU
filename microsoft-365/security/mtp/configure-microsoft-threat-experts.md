---
title: Настройка и управление эксперты Майкрософт по угрозам с помощью Microsoft 365 Defender
description: Подпишитесь на экспертов Microsoft Threats через Microsoft 365 Defender, чтобы настроить, управлять и использовать его в ежедневных операциях по безопасности и администрировании безопасности.
keywords: эксперты Майкрософт по угрозам, служба управляемой охоты на угрозы, MTE, служба управляемой охоты Microsoft
search.product: Windows 10
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-maave
author: martyav
localization_priority: normal
manager: dansimp
audience: ITPro
ms.topic: article
ms.openlocfilehash: 0ccb8482dae94de4a9f43a5ecaf7c701e6dd82a5
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844794"
---
# <a name="configure-and-manage-microsoft-threat-experts-capabilities-through-microsoft-365-defender"></a><span data-ttu-id="f4044-104">Настройка и управление эксперты Майкрософт по угрозам с помощью Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f4044-104">Configure and manage Microsoft Threat Experts capabilities through Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="f4044-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="f4044-105">**Applies to:**</span></span>

- [<span data-ttu-id="f4044-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f4044-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- [<span data-ttu-id="f4044-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="f4044-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Prerelease](../includes/prerelease.md)]

## <a name="before-you-begin"></a><span data-ttu-id="f4044-108">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="f4044-108">Before you begin</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f4044-109">Перед подачей заявки обязательно обсудите требования к требованиям для эксперты Майкрософт по угрозам — служба управляемых уведомлений об угрозах с поставщиком технической службы Майкрософт и командой учетных записей.</span><span class="sxs-lookup"><span data-stu-id="f4044-109">Before you apply, make sure to discuss the eligibility requirements for the Microsoft Threat Experts – Targeted Attack Notifications managed threat hunting service with your Microsoft Technical Service provider and account team.</span></span>

<span data-ttu-id="f4044-110">Для получения целевых уведомлений об атаке необходимо развернуть Microsoft 365 Defender с зарегистрированными устройствами.</span><span class="sxs-lookup"><span data-stu-id="f4044-110">To receive targeted attack notifications, you'll need to have Microsoft 365 Defender deployed with devices enrolled.</span></span> <span data-ttu-id="f4044-111">Затем отправьте приложение на портале M365 для эксперты Майкрософт по угрозам - targeted Attack Notifications.</span><span class="sxs-lookup"><span data-stu-id="f4044-111">Then, submit an application through the M365 portal for Microsoft Threat Experts - Targeted Attack Notifications.</span></span>

<span data-ttu-id="f4044-112">Свяжитесь с командой учетных записей или представителем Майкрософт, чтобы подписаться на эксперты Майкрософт по угрозам - Эксперты по запросу.</span><span class="sxs-lookup"><span data-stu-id="f4044-112">Contact your account team or Microsoft representative to subscribe to Microsoft Threat Experts - Experts on Demand.</span></span> <span data-ttu-id="f4044-113">Эксперты по запросу позволяют проконсультироваться с нашими экспертами по угрозам о том, как защитить организацию от соответствующих обнаружений и противников.</span><span class="sxs-lookup"><span data-stu-id="f4044-113">Experts on Demand lets you consult with our threat experts on how to protect your organization from relevant detections and adversaries.</span></span>

## <a name="apply-for-microsoft-threat-experts---targeted-attack-notifications-service"></a><span data-ttu-id="f4044-114">Apply for эксперты Майкрософт по угрозам - служба уведомлений о целевых атаках</span><span class="sxs-lookup"><span data-stu-id="f4044-114">Apply for Microsoft Threat Experts - Targeted Attack Notifications service</span></span>

<span data-ttu-id="f4044-115">Если у вас уже есть Microsoft Defender для конечной точки и Microsoft 365 Defender, вы можете подать заявку на эксперты Майкрософт по угрозам — целевые уведомления об атаке через портал Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="f4044-115">If you already have Microsoft Defender for Endpoint and Microsoft 365 Defender, you can apply for Microsoft Threat Experts – Targeted Attack Notifications through their Microsoft 365 Defender portal.</span></span>  <span data-ttu-id="f4044-116">Целевые уведомления об атаках помогут определить наиболее важные угрозы для вашей организации, чтобы вы могли быстро реагировать на них.</span><span class="sxs-lookup"><span data-stu-id="f4044-116">Targeted attack notifications grant you special insight and analysis to help identify the most critical threats to your organization, so you can respond to them quickly.</span></span>

1. <span data-ttu-id="f4044-117">Из области навигации перейдите в Параметры > конечные точки > **общие > расширенные** функции > эксперты Майкрософт по угрозам - целевые уведомления о атаке .</span><span class="sxs-lookup"><span data-stu-id="f4044-117">From the navigation pane, go to **Settings > Endpoints > General > Advanced features > Microsoft Threat Experts - Targeted Attack Notifications**.</span></span>

2. <span data-ttu-id="f4044-118">Нажмите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="f4044-118">Select **Apply**.</span></span>

    ![Изображение параметров эксперты Майкрософт по угрозам](../../media/mte/mte-collaboratewithmte.png)

3. <span data-ttu-id="f4044-120">Введите свое имя и адрес электронной почты, чтобы Корпорация Майкрософт связалась с вами по поводу вашего приложения.</span><span class="sxs-lookup"><span data-stu-id="f4044-120">Enter your name and email address so that Microsoft can contact you about your application.</span></span>

    ![Изображение эксперты Майкрософт по угрозам приложения](../../media/mte/mte-apply.png)

4. <span data-ttu-id="f4044-122">Прочитайте [заявление о конфиденциальности,](https://privacy.microsoft.com/en-us/privacystatement)а затем **выберите Отправка,** когда вы закончили.</span><span class="sxs-lookup"><span data-stu-id="f4044-122">Read the [privacy statement](https://privacy.microsoft.com/en-us/privacystatement), then select **Submit** when you're done.</span></span> <span data-ttu-id="f4044-123">Вы получите приветственный адрес электронной почты после утверждения приложения.</span><span class="sxs-lookup"><span data-stu-id="f4044-123">You'll receive a welcome email once your application is approved.</span></span>

    ![Изображение подтверждения эксперты Майкрософт по угрозам приложения](../../media/mte/mte-applicationconfirmation.png)

5. <span data-ttu-id="f4044-125">После получения приветствия электронной почты вы автоматически начнете получать целевые уведомления об атаке.</span><span class="sxs-lookup"><span data-stu-id="f4044-125">After you receive your welcome email, you'll automatically start receiving targeted attack notifications.</span></span>

6. <span data-ttu-id="f4044-126">Вы можете проверить свой статус, посетив Параметры > конечные точки > **общие > расширенные функции**.</span><span class="sxs-lookup"><span data-stu-id="f4044-126">You can verify your status by visiting **Settings > Endpoints > General > Advanced features**.</span></span> <span data-ttu-id="f4044-127">После утверждения переключатель **эксперты Майкрософт по угрозам —** целевое уведомление об атаке будет виден и **включен.**</span><span class="sxs-lookup"><span data-stu-id="f4044-127">Once approved, the **Microsoft Threat Experts - Targeted Attack Notification** toggle will be visible and switched **On**.</span></span>

## <a name="where-youll-see-the-targeted-attack-notifications-from-microsoft-threat-experts"></a><span data-ttu-id="f4044-128">Где вы увидите целевые уведомления об атаке из эксперты Майкрософт по угрозам</span><span class="sxs-lookup"><span data-stu-id="f4044-128">Where you'll see the targeted attack notifications from Microsoft Threat Experts</span></span>

<span data-ttu-id="f4044-129">Вы можете получать целевое уведомление об атаке из эксперты Майкрософт по угрозам с помощью следующих сред:</span><span class="sxs-lookup"><span data-stu-id="f4044-129">You can receive targeted attack notification from Microsoft Threat Experts through the following mediums:</span></span>

- <span data-ttu-id="f4044-130">Страница инцидентов Microsoft 365 **защитника**</span><span class="sxs-lookup"><span data-stu-id="f4044-130">The Microsoft 365 Defender portal's **Incidents** page</span></span>
- <span data-ttu-id="f4044-131">Панель оповещений портала Microsoft 365 **Defender**</span><span class="sxs-lookup"><span data-stu-id="f4044-131">The Microsoft 365 Defender portal's **Alerts** dashboard</span></span>
- <span data-ttu-id="f4044-132">OData оповещения [API и](/windows/security/threat-protection/microsoft-defender-atp/get-alerts) [REST API](/windows/security/threat-protection/microsoft-defender-atp/pull-alerts-using-rest-api)</span><span class="sxs-lookup"><span data-stu-id="f4044-132">OData alerting [API](/windows/security/threat-protection/microsoft-defender-atp/get-alerts) and [REST API](/windows/security/threat-protection/microsoft-defender-atp/pull-alerts-using-rest-api)</span></span>
- <span data-ttu-id="f4044-133">[Таблица DeviceAlertEvents](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-devicealertevents-table) в расширенных охотах</span><span class="sxs-lookup"><span data-stu-id="f4044-133">[DeviceAlertEvents](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-devicealertevents-table) table in Advanced hunting</span></span>
- <span data-ttu-id="f4044-134">Почтовый ящик, если вы хотите, чтобы целевые уведомления о атаке были отправлены вам по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="f4044-134">Your inbox, if you choose to have targeted attack notifications sent to you via email.</span></span> <span data-ttu-id="f4044-135">См. [ниже правило "Создание уведомления по электронной почте".](#create-an-email-notification-rule)</span><span class="sxs-lookup"><span data-stu-id="f4044-135">See [Create an email notification rule](#create-an-email-notification-rule) below.</span></span>

### <a name="create-an-email-notification-rule"></a><span data-ttu-id="f4044-136">Создание правила уведомления по электронной почте</span><span class="sxs-lookup"><span data-stu-id="f4044-136">Create an email notification rule</span></span>

<span data-ttu-id="f4044-137">Вы можете создать правила для отправки уведомлений электронной почты для получателей уведомлений.</span><span class="sxs-lookup"><span data-stu-id="f4044-137">You can create rules to send email notifications for notification recipients.</span></span> <span data-ttu-id="f4044-138">Дополнительные сведения см. в  [публикации Configure alerts](/windows/security/threat-protection/microsoft-defender-atp/configure-email-notifications) to create, edit, delete или troubleshoot email notification.</span><span class="sxs-lookup"><span data-stu-id="f4044-138">For full details, see  [Configure alert notifications](/windows/security/threat-protection/microsoft-defender-atp/configure-email-notifications) to create, edit, delete, or troubleshoot email notification.</span></span>

## <a name="view-targeted-attack-notifications"></a><span data-ttu-id="f4044-139">Просмотр целевых уведомлений об атаке</span><span class="sxs-lookup"><span data-stu-id="f4044-139">View targeted attack notifications</span></span>

<span data-ttu-id="f4044-140">Вы начнете получать целевое уведомление об атаке эксперты Майкрософт по угрозам электронной почты после настройки системы для получения уведомления электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f4044-140">You'll start receiving targeted attack notification from Microsoft Threat Experts in your email after you have configured your system to receive email notification.</span></span>

1. <span data-ttu-id="f4044-141">Выберите ссылку в электронной почте, чтобы перейти к соответствующему контексту оповещений на панели мониторинга с тегами **экспертов Threat**.</span><span class="sxs-lookup"><span data-stu-id="f4044-141">Select the link in the email to go to the corresponding alert context in the dashboard tagged with **Threat experts**.</span></span>

2. <span data-ttu-id="f4044-142">На странице **Оповещений** выберите ту же тему оповещения, что и полученную в электронной почте, чтобы просмотреть дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="f4044-142">From the **Alerts** page, select the same alert topic as the one you received in the email, to view further details.</span></span>

## <a name="subscribe-to-microsoft-threat-experts---experts-on-demand"></a><span data-ttu-id="f4044-143">Подписка на эксперты Майкрософт по угрозам - Эксперты по запросу</span><span class="sxs-lookup"><span data-stu-id="f4044-143">Subscribe to Microsoft Threat Experts - Experts on Demand</span></span>

<span data-ttu-id="f4044-144">Если вы уже клиент Microsoft Defender для конечных точек, вы можете связаться со своим представителем Майкрософт, чтобы подписаться на эксперты Майкрософт по угрозам - Эксперты по запросу.</span><span class="sxs-lookup"><span data-stu-id="f4044-144">If you're already a Microsoft Defender for Endpoint customer, you can contact your Microsoft representative to subscribe to Microsoft Threat Experts - Experts on Demand.</span></span>

## <a name="consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization"></a><span data-ttu-id="f4044-145">Проконсультируйтесь с экспертом по угрозам Майкрософт о подозрительных действиях в области кибербезопасности в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="f4044-145">Consult a Microsoft threat expert about suspicious cybersecurity activities in your organization</span></span>

<span data-ttu-id="f4044-146">Вы можете связаться эксперты Майкрософт по угрозам изнутри портала Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="f4044-146">You can contact Microsoft Threat Experts from inside the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="f4044-147">Эксперты помогут вам понять сложные угрозы и целевые уведомления об атаке.</span><span class="sxs-lookup"><span data-stu-id="f4044-147">Experts can help you understand complex threats and targeted attack notifications.</span></span> <span data-ttu-id="f4044-148">Дополнительные сведения о оповещениях и инцидентах, а также рекомендации по обработке компрометации.</span><span class="sxs-lookup"><span data-stu-id="f4044-148">Partner with experts for further details about alerts and incidents, or advice on handling compromise.</span></span> <span data-ttu-id="f4044-149">Получение сведений о контексте сведении об угрозах, описанного панелью мониторинга портала.</span><span class="sxs-lookup"><span data-stu-id="f4044-149">Gain insight into the threat intelligence context described by your portal dashboard.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="f4044-150">Запросы оповещений, связанные с настраиваемыми данными разведки угроз в организации, в настоящее время не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="f4044-150">Alert inquiries related to your organization's customized threat intelligence data are not currently supported.</span></span> <span data-ttu-id="f4044-151">Подробные сведения проконсультируйтесь с вашей службой безопасности или командой реагирования на инциденты.</span><span class="sxs-lookup"><span data-stu-id="f4044-151">Consult with your security operations or incident response team for details.</span></span>
> - <span data-ttu-id="f4044-152">Для отправки  запроса через форму эксперта по угрозам в центре безопасности на портале Microsoft 365 Defender необходимо иметь разрешение на управление настройками **безопасности.**</span><span class="sxs-lookup"><span data-stu-id="f4044-152">You need to have the **Manage security settings in Security Center** permission in the Microsoft 365 Defender portal to submit an inquiry through the **Consult a threat expert** form.</span></span>

1. <span data-ttu-id="f4044-153">Перейдите на страницу портала, связанную с сведениями, которые необходимо исследовать: например, **Device,** **Alert** или **Incident**.</span><span class="sxs-lookup"><span data-stu-id="f4044-153">Navigate to the portal page related to the information that you'd like to investigate: for example, **Device**, **Alert**, or **Incident**.</span></span> <span data-ttu-id="f4044-154">Убедитесь, что страница портала, связанная с запросом, просматривается перед отправкой запроса на расследование.</span><span class="sxs-lookup"><span data-stu-id="f4044-154">Make sure that the portal page related to your inquiry is in view before you send an investigation request.</span></span>

2. <span data-ttu-id="f4044-155">Из верхнего меню **выберите? Обратитесь к эксперту по угрозам.**</span><span class="sxs-lookup"><span data-stu-id="f4044-155">From the top menu, select **? Consult a threat expert**.</span></span>

    ![Изображение эксперты Майкрософт по угрозам экспертов по запросу из меню](../../media/mte/incidents-action-mte-highlighted.png)

    <span data-ttu-id="f4044-157">Откроется экран вылетов.</span><span class="sxs-lookup"><span data-stu-id="f4044-157">A flyout screen will open.</span></span>

    <span data-ttu-id="f4044-158">В загонах будет указано, находитесь ли вы на пробной подписке, или полное эксперты Майкрософт по угрозам - подписка экспертов по запросу.</span><span class="sxs-lookup"><span data-stu-id="f4044-158">The header will indicate if you are on a trial subscription, or a full Microsoft Threat Experts - Experts on-Demand subscription.</span></span>

    ![Изображение экспертов эксперты Майкрософт по угрозам на экране пробной подписки На запрос](../../media/mte/mte-trial.png)

    <span data-ttu-id="f4044-160">Поле **темы** Исследования уже будет заполнено ссылкой на соответствующую страницу для вашего запроса.</span><span class="sxs-lookup"><span data-stu-id="f4044-160">The **Investigation topic** field will already be populated with the link to the relevant page for your request.</span></span>

3. <span data-ttu-id="f4044-161">В следующем поле укайте достаточно информации, чтобы эксперты Майкрософт по угрозам контекста для начала расследования.</span><span class="sxs-lookup"><span data-stu-id="f4044-161">In the next field, provide enough information to give the Microsoft Threat Experts enough context to start the investigation.</span></span>

4. <span data-ttu-id="f4044-162">Введите адрес электронной почты, который вы хотите использовать, чтобы соответствовать эксперты Майкрософт по угрозам.</span><span class="sxs-lookup"><span data-stu-id="f4044-162">Enter the email address that you'd like to use to correspond with Microsoft Threat Experts.</span></span>

> [!NOTE]
> <span data-ttu-id="f4044-163">Если вы хотите отслеживать состояние дел "Эксперты по запросу" с помощью Центра служб Майкрософт, перенаправление к техническому менеджеру учетной записи.</span><span class="sxs-lookup"><span data-stu-id="f4044-163">If you would like to track the status of your Experts on Demand cases through Microsoft Services Hub, reach out to your technical account manager.</span></span>

<span data-ttu-id="f4044-164">Просмотрите это видео для краткого обзора центра служб Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f4044-164">Watch this video for a quick overview of the Microsoft Services Hub.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4pk9f]

## <a name="sample-investigation-topics"></a><span data-ttu-id="f4044-165">Примеры тем исследования</span><span class="sxs-lookup"><span data-stu-id="f4044-165">Sample investigation topics</span></span>

### <a name="alert-information"></a><span data-ttu-id="f4044-166">Сведения об оповещении</span><span class="sxs-lookup"><span data-stu-id="f4044-166">Alert information</span></span>

- <span data-ttu-id="f4044-167">Мы увидели новый тип оповещений для двоичного двоичного параметра living-off-the-land.</span><span class="sxs-lookup"><span data-stu-id="f4044-167">We saw a new type of alert for a living-off-the-land binary.</span></span> <span data-ttu-id="f4044-168">Мы можем предоставить iD оповещений.</span><span class="sxs-lookup"><span data-stu-id="f4044-168">We can provide the alert ID.</span></span> <span data-ttu-id="f4044-169">Можете ли вы рассказать нам больше об этом оповещении и о том, как мы можем исследовать его далее?</span><span class="sxs-lookup"><span data-stu-id="f4044-169">Can you tell us more about this alert and how we can investigate it further?</span></span>
- <span data-ttu-id="f4044-170">Мы наблюдали две аналогичные атаки, которые пытаются выполнять вредоносные скрипты PowerShell, но создают различные оповещения.</span><span class="sxs-lookup"><span data-stu-id="f4044-170">We've observed two similar attacks, which both try to execute malicious PowerShell scripts but generate different alerts.</span></span> <span data-ttu-id="f4044-171">Одна из них — "Подозрительная командная строка PowerShell", а другая — "Вредоносный файл был обнаружен на основе показаний, предоставленных O365".</span><span class="sxs-lookup"><span data-stu-id="f4044-171">One is "Suspicious PowerShell command line" and the other is "A malicious file was detected based on indication provided by O365".</span></span> <span data-ttu-id="f4044-172">В чем разница?</span><span class="sxs-lookup"><span data-stu-id="f4044-172">What is the difference?</span></span>
- <span data-ttu-id="f4044-173">Сегодня мы получили нечетное оповещение о ненормальном количестве неудались логинов с устройства пользователя высокого профиля.</span><span class="sxs-lookup"><span data-stu-id="f4044-173">We received an odd alert today about an abnormal number of failed logins from a high profile user’s device.</span></span> <span data-ttu-id="f4044-174">Мы не можем найти дополнительных доказательств этих попыток.</span><span class="sxs-lookup"><span data-stu-id="f4044-174">We can't find any further evidence for these attempts.</span></span> <span data-ttu-id="f4044-175">Как Microsoft 365 Defender увидеть эти попытки?</span><span class="sxs-lookup"><span data-stu-id="f4044-175">How can Microsoft 365 Defender see these attempts?</span></span> <span data-ttu-id="f4044-176">За каким типом логинов ведется мониторинг?</span><span class="sxs-lookup"><span data-stu-id="f4044-176">What type of logins are being monitored?</span></span>
- <span data-ttu-id="f4044-177">Можете ли вы дать дополнительные сведения о оповещении о предупреждении", "Подозрительное поведение системной утилиты было замечено"?</span><span class="sxs-lookup"><span data-stu-id="f4044-177">Can you give more context or insight about the alert, "Suspicious behavior by a system utility was observed"?</span></span>
- <span data-ttu-id="f4044-178">Я заметил предупреждение под названием "Создание правила переадресации/перенаправления".</span><span class="sxs-lookup"><span data-stu-id="f4044-178">I observed an alert titled "Creation of forwarding/redirect rule".</span></span> <span data-ttu-id="f4044-179">Я считаю, что эта деятельность является доброкачественной.</span><span class="sxs-lookup"><span data-stu-id="f4044-179">I believe the activity is benign.</span></span> <span data-ttu-id="f4044-180">Можете ли вы рассказать мне, почему я получил предупреждение?</span><span class="sxs-lookup"><span data-stu-id="f4044-180">Can you tell me why I received an alert?</span></span>

### <a name="possible-machine-compromise"></a><span data-ttu-id="f4044-181">Возможный компьютерный компромисс</span><span class="sxs-lookup"><span data-stu-id="f4044-181">Possible machine compromise</span></span>

- <span data-ttu-id="f4044-182">Можете ли вы помочь объяснить, почему на многих устройствах в нашей организации мы видим сообщение или оповещение о "Неизвестном процессе"?</span><span class="sxs-lookup"><span data-stu-id="f4044-182">Can you help explain why we see a message or alert for "Unknown process observed" on many devices in our organization?</span></span> <span data-ttu-id="f4044-183">Мы ценим любые входные данные для уточнения того, связано ли это сообщение или оповещение с вредоносными действиями.</span><span class="sxs-lookup"><span data-stu-id="f4044-183">We appreciate any input to clarify whether this message or alert is related to malicious activity.</span></span>
- <span data-ttu-id="f4044-184">Можете ли вы проверить возможный компромисс в следующей системе, начиная с прошлой недели?</span><span class="sxs-lookup"><span data-stu-id="f4044-184">Can you help validate a possible compromise on the following system, dating from last week?</span></span> <span data-ttu-id="f4044-185">Он ведет себя так же, как и предыдущее обнаружение вредоносных программ в той же системе шесть месяцев назад.</span><span class="sxs-lookup"><span data-stu-id="f4044-185">It's behaving similarly as a previous malware detection on the same system six months ago.</span></span>

### <a name="threat-intelligence-details"></a><span data-ttu-id="f4044-186">Сведения о разведке угроз</span><span class="sxs-lookup"><span data-stu-id="f4044-186">Threat intelligence details</span></span>

- <span data-ttu-id="f4044-187">Обнаружена фишинговая электронная почта, которая передала пользователю вредоносный документ Word.</span><span class="sxs-lookup"><span data-stu-id="f4044-187">We detected a phishing email that delivered a malicious Word document to a user.</span></span> <span data-ttu-id="f4044-188">Документ вызвал серию подозрительных событий, которые вызвали несколько оповещений для определенного семейства вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="f4044-188">The document caused a series of suspicious events, which triggered multiple alerts for a particular malware family.</span></span> <span data-ttu-id="f4044-189">Есть ли у вас сведения об этой вредоносной программе?</span><span class="sxs-lookup"><span data-stu-id="f4044-189">Do you have any information on this malware?</span></span> <span data-ttu-id="f4044-190">Если да, можете ли вы отправить нам ссылку?</span><span class="sxs-lookup"><span data-stu-id="f4044-190">If yes, can you send us a link?</span></span>
- <span data-ttu-id="f4044-191">Недавно мы увидели сообщение в блоге об угрозе, которая направлена на нашу отрасль.</span><span class="sxs-lookup"><span data-stu-id="f4044-191">We recently saw a blog post about a threat that is targeting our industry.</span></span> <span data-ttu-id="f4044-192">Можете ли вы помочь нам понять, какую защиту Microsoft 365 Defender от этого субъекта угроз?</span><span class="sxs-lookup"><span data-stu-id="f4044-192">Can you help us understand what protection Microsoft 365 Defender provides against this threat actor?</span></span>
- <span data-ttu-id="f4044-193">Недавно мы наблюдали фишинговую кампанию, проведенную против нашей организации.</span><span class="sxs-lookup"><span data-stu-id="f4044-193">We recently observed a phishing campaign conducted against our organization.</span></span> <span data-ttu-id="f4044-194">Можете ли вы сообщить нам, была ли эта цель направлена конкретно на нашу компанию или вертикаль?</span><span class="sxs-lookup"><span data-stu-id="f4044-194">Can you tell us if this was targeted specifically to our company or vertical?</span></span>

### <a name="microsoft-threat-experts-alert-communications"></a><span data-ttu-id="f4044-195">эксперты Майкрософт по угрозам оповещений</span><span class="sxs-lookup"><span data-stu-id="f4044-195">Microsoft Threat Experts’ alert communications</span></span>

- <span data-ttu-id="f4044-196">Может ли ваша группа реагирования на инциденты помочь нам в решении целевого уведомления об атаке, которое мы получили?</span><span class="sxs-lookup"><span data-stu-id="f4044-196">Can your incident response team help us address the targeted attack notification that we got?</span></span>
- <span data-ttu-id="f4044-197">Мы получили это целевое уведомление об атаке из эксперты Майкрософт по угрозам.</span><span class="sxs-lookup"><span data-stu-id="f4044-197">We received this targeted attack notification from Microsoft Threat Experts.</span></span> <span data-ttu-id="f4044-198">У нас нет собственной группы реагирования на инциденты.</span><span class="sxs-lookup"><span data-stu-id="f4044-198">We don’t have our own incident response team.</span></span> <span data-ttu-id="f4044-199">Что мы можем сделать сейчас и как сдержать инцидент?</span><span class="sxs-lookup"><span data-stu-id="f4044-199">What can we do now, and how can we contain the incident?</span></span>
- <span data-ttu-id="f4044-200">Мы получили целевое уведомление об атаке из эксперты Майкрософт по угрозам.</span><span class="sxs-lookup"><span data-stu-id="f4044-200">We received a targeted attack notification from Microsoft Threat Experts.</span></span> <span data-ttu-id="f4044-201">Какие данные вы можете предоставить нам, чтобы мы могли передать нашей группе реагирования на инциденты?</span><span class="sxs-lookup"><span data-stu-id="f4044-201">What data can you provide to us that we can pass on to our incident response team?</span></span>

> [!NOTE]
> <span data-ttu-id="f4044-202">эксперты Майкрософт по угрозам — это служба управляемой охоты на угрозы, а не служба реагирования на инциденты.</span><span class="sxs-lookup"><span data-stu-id="f4044-202">Microsoft Threat Experts is a managed threat hunting service and not an incident response service.</span></span> <span data-ttu-id="f4044-203">Тем не менее, эксперты могут без проблем перенаупрестить расследование в службы группы обнаружения и реагирования Microsoft Cybersecurity Solutions Group (CSG) при необходимости.</span><span class="sxs-lookup"><span data-stu-id="f4044-203">However, the experts can seamlessly transition the investigation to Microsoft Cybersecurity Solutions Group (CSG)'s Detection and Response Team (DART) services, when necessary.</span></span> <span data-ttu-id="f4044-204">Вы также можете взаимодействовать со своей командой реагирования на инциденты для устранения проблем, которые требуют реагирования на инциденты.</span><span class="sxs-lookup"><span data-stu-id="f4044-204">You can also opt to engage with your own incident response team to address issues that requires an incident response.</span></span>

## <a name="scenario"></a><span data-ttu-id="f4044-205">Сценарий</span><span class="sxs-lookup"><span data-stu-id="f4044-205">Scenario</span></span>

### <a name="receive-a-progress-report-about-your-managed-hunting-inquiry"></a><span data-ttu-id="f4044-206">Получение отчета о ходе выполнения управляемого запроса на охоту</span><span class="sxs-lookup"><span data-stu-id="f4044-206">Receive a progress report about your managed hunting inquiry</span></span>

<span data-ttu-id="f4044-207">Ответ от эксперты Майкрософт по угрозам зависит от вашего запроса.</span><span class="sxs-lookup"><span data-stu-id="f4044-207">The response from Microsoft Threat Experts will vary according to your inquiry.</span></span> <span data-ttu-id="f4044-208">Обычно вы получите один из следующих ответов:</span><span class="sxs-lookup"><span data-stu-id="f4044-208">You'll generally receive one of the following responses:</span></span>

- <span data-ttu-id="f4044-209">Дополнительные сведения необходимы для продолжения расследования</span><span class="sxs-lookup"><span data-stu-id="f4044-209">More information is needed to continue with the investigation</span></span>
- <span data-ttu-id="f4044-210">Для определения технического контекста необходим файл или несколько примеров файлов.</span><span class="sxs-lookup"><span data-stu-id="f4044-210">A file or several file samples are needed to determine the technical context</span></span>
- <span data-ttu-id="f4044-211">Для расследования требуется больше времени</span><span class="sxs-lookup"><span data-stu-id="f4044-211">Investigation requires more time</span></span>
- <span data-ttu-id="f4044-212">Начальной информации было достаточно, чтобы завершить расследование</span><span class="sxs-lookup"><span data-stu-id="f4044-212">Initial information was enough to conclude the investigation</span></span>

<span data-ttu-id="f4044-213">Если эксперт запрашивает дополнительные сведения или примеры файлов, важно быстро реагировать, чтобы сохранить ход расследования.</span><span class="sxs-lookup"><span data-stu-id="f4044-213">If an expert requests more information or file samples, it's crucial to respond quickly to keep the investigation moving.</span></span>

## <a name="see-also"></a><span data-ttu-id="f4044-214">См. также</span><span class="sxs-lookup"><span data-stu-id="f4044-214">See also</span></span>

- [<span data-ttu-id="f4044-215">Обзор экспертов Майкрософт по угрозам</span><span class="sxs-lookup"><span data-stu-id="f4044-215">Microsoft Threat Experts overview</span></span>](microsoft-threat-experts.md)
