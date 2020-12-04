---
title: Пошаговое руководство по подделке анализа
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать, как работает аналитика подделки. Они могут быстро определить, какие отправители подлиннее отправляют сообщения в свои организации из доменов, которые не проходят проверку подлинности электронной почты (SPF, DKIM или DMARC).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6f5ebd0fd42d17354eeb1e03c946ac5446c3667c
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572745"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a><span data-ttu-id="ca09a-104">Пошаговое руководство по подделке анализа в защитнике Майкрософт для Office 365</span><span class="sxs-lookup"><span data-stu-id="ca09a-104">Walkthrough - Spoof intelligence insight in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="ca09a-105">В организациях Microsoft 365 с защитником для Office 365 можно использовать средство анализа сведений о подделке для быстрого определения того, какие отправители подлиннее отправляют сообщения электронной почты, не прошедшие проверку подлинности (сообщения из доменов, которые не проходят проверки SPF, DKIM или DMARC).</span><span class="sxs-lookup"><span data-stu-id="ca09a-105">In Microsoft 365 organizations with Defender for Office 365, you can use the Spoof intelligence insight to quickly determine which senders are legitimately sending you unauthenticated email (messages from domains that don't pass SPF, DKIM, or DMARC checks).</span></span>

<span data-ttu-id="ca09a-106">Разрешая известным отправителям отправлять поддельные сообщения из известных расположений, вы можете сократить ложные срабатывания (хороший адрес электронной почты отмечен как ошибочный).</span><span class="sxs-lookup"><span data-stu-id="ca09a-106">By allowing known senders to send spoofed messages from known locations, you can reduce false positives (good email marked as bad).</span></span> <span data-ttu-id="ca09a-107">Отслеживая разрешенных отправителей, вы предоставляете дополнительный уровень безопасности, чтобы предотвратить поступление небезопасных сообщений в Организации.</span><span class="sxs-lookup"><span data-stu-id="ca09a-107">By monitoring the allowed spoofed senders, you provide an additional layer of security to prevent unsafe messages from arriving in your organization.</span></span>

<span data-ttu-id="ca09a-108">Дополнительные сведения об отчетах и аналитических данных можно найти [в статье отчеты и аналитика центра безопасности & соответствия требованиям](reports-and-insights-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="ca09a-108">For more information about reports and insights, see [Reports and insights in the Security & Compliance Center](reports-and-insights-in-security-and-compliance.md).</span></span>

<span data-ttu-id="ca09a-109">Это пошаговое руководство является одним из нескольких для центра безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="ca09a-109">This walkthrough is one of several for the Security & Compliance Center.</span></span> <span data-ttu-id="ca09a-110">Сведения о том, как переходить по отчетам и аналитическим сведениям, можно найти в пошаговых руководствах раздела " [связанные темы](#related-topics) ".</span><span class="sxs-lookup"><span data-stu-id="ca09a-110">To about navigating reports and insights, see the walkthroughs in the [Related topics](#related-topics) section.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ca09a-111">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="ca09a-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ca09a-112">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="ca09a-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="ca09a-113">Чтобы перейти непосредственно на страницу **панели мониторинга безопасности** , используйте <https://protection.office.com/searchandinvestigation/dashboard> .</span><span class="sxs-lookup"><span data-stu-id="ca09a-113">To go directly to the **Security dashboard** page, use <https://protection.office.com/searchandinvestigation/dashboard>.</span></span>

  <span data-ttu-id="ca09a-114">В центре безопасности & соответствия требованиям вы можете просматривать сведения о подделке для нескольких панелей мониторинга.</span><span class="sxs-lookup"><span data-stu-id="ca09a-114">You can view the Spoof intelligence insight from more than one dashboard in the Security & Compliance Center.</span></span> <span data-ttu-id="ca09a-115">Независимо от того, какая панель мониторинга отображается, сведения о ней представлены одинаково и позволяют быстро выполнять те же задачи.</span><span class="sxs-lookup"><span data-stu-id="ca09a-115">Regardless of which dashboard you're looking at, the insight provides the same details and allows you to quickly perform the same tasks.</span></span>

- <span data-ttu-id="ca09a-116">Прежде чем выполнять процедуры, описанные в этой статье, необходимо назначить разрешения в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="ca09a-116">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="ca09a-117">**Управление организацией**</span><span class="sxs-lookup"><span data-stu-id="ca09a-117">**Organization Management**</span></span>
  - <span data-ttu-id="ca09a-118">**Администратор безопасности**</span><span class="sxs-lookup"><span data-stu-id="ca09a-118">**Security Administrator**</span></span>
  - <span data-ttu-id="ca09a-119">**Средство чтения безопасности**</span><span class="sxs-lookup"><span data-stu-id="ca09a-119">**Security Reader**</span></span>
  - <span data-ttu-id="ca09a-120">**Глобальный читатель**</span><span class="sxs-lookup"><span data-stu-id="ca09a-120">**Global Reader**</span></span>

  <span data-ttu-id="ca09a-121">**Примечание**: при добавлении пользователей в соответствующую роль Azure Active Directory в центре администрирования Microsoft 365 пользователям предоставляются необходимые разрешения в центре безопасности & соответствия требованиям _и_ разрешениях для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ca09a-121">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="ca09a-122">Дополнительные сведения см. в статье [О ролях администраторов](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="ca09a-122">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

- <span data-ttu-id="ca09a-123">Вы включаете и отключаете логику подделки в политиках защиты от фишинга в защитнике Майкрософт для Office 365.</span><span class="sxs-lookup"><span data-stu-id="ca09a-123">You enable and disable spoof intelligence in anti-phishing policies in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="ca09a-124">Дополнительные сведения см. [в разделе Настройка политик защиты от фишинга в защитнике Майкрософт для Office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ca09a-124">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="ca09a-125">Чтобы использовать логику подделки для отслеживания отправителей, которые отправляют сообщения, не прошедших проверку подлинности, и управления ими, ознакомьтесь со статьей [Настройка логики анализа в Microsoft 365](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="ca09a-125">To use spoof intelligence to monitor and manage senders who are sending you unauthenticated messages, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a><span data-ttu-id="ca09a-126">Откройте центр контроля допуска подделки в центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="ca09a-126">Open the spoof intelligence insight in the Security & Compliance Center</span></span>

1. <span data-ttu-id="ca09a-127">В центре безопасности & соответствия требованиям перейдите на панель мониторинга **управления угрозами** \> **.**</span><span class="sxs-lookup"><span data-stu-id="ca09a-127">In the Security & Compliance Center, go to **Threat Management** \> **Dashboard.**</span></span>

2. <span data-ttu-id="ca09a-128">В строке **Insights** найдите один из следующих элементов:</span><span class="sxs-lookup"><span data-stu-id="ca09a-128">In the **Insights** row, look for one of the following items:</span></span>

   - <span data-ttu-id="ca09a-129">**Аналитика подделки включена**: Insights — это **домены с поддельным именем, не прошедшие проверку подлинности за прошедшие 30 дней**.</span><span class="sxs-lookup"><span data-stu-id="ca09a-129">**Spoof intelligence is enabled**: The insight is named **Spoofed domains that failed authentication of the past 30 days**.</span></span> <span data-ttu-id="ca09a-130">Этот параметр используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ca09a-130">This is the default.</span></span>
   - <span data-ttu-id="ca09a-131">**Аналитика подделки отключена**: представление " **Включение защиты от спуфинга**" и нажатие этой кнопки позволяет включить аналитику подделки.</span><span class="sxs-lookup"><span data-stu-id="ca09a-131">**Spoof intelligence is disabled**: The insight in named **Enable Spoof Protection**, and clicking on it allows you to enable spoof intelligence.</span></span>

3. <span data-ttu-id="ca09a-132">В панели мониторинга отображается следующая информация:</span><span class="sxs-lookup"><span data-stu-id="ca09a-132">The insight on the dashboard shows you information like this:</span></span>

   ![Снимок экрана анализа анализа подделки](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   <span data-ttu-id="ca09a-134">Эта аналитика имеет два режима:</span><span class="sxs-lookup"><span data-stu-id="ca09a-134">This insight has two modes:</span></span>

   - <span data-ttu-id="ca09a-135">**Режим понимания**: Если функция "анализ подделки" включена, в сведениях о количестве сообщений, на которые повлияла функция анализа подделки за прошедшие 30 дней, отображается подробное представление.</span><span class="sxs-lookup"><span data-stu-id="ca09a-135">**Insight mode**: If spoof intelligence is enabled, the insight shows you how many messages were impacted by our spoof intelligence capabilities over the past 30 days.</span></span>

   - <span data-ttu-id="ca09a-136">В **режиме "что если**": Если логика подделки отключена, то сведения о количестве *сообщений, на которые повлияла* функция анализа подделки за прошедшие 30 дней, отображаются на экране.</span><span class="sxs-lookup"><span data-stu-id="ca09a-136">**What if mode**: If spoof intelligence is disabled, then the insight shows you how many messages *would* have been impacted by our spoof intelligence capabilities over the past 30 days.</span></span>

   <span data-ttu-id="ca09a-137">В обоих случаях поддельные домены, отображаемые в разделе Insights, делятся на две категории: **подозрительные** и **неподозрительные пары** доменов.</span><span class="sxs-lookup"><span data-stu-id="ca09a-137">Either way, the spoofed domains displayed in the insight are separated into two categories: **Suspicious domain pairs** and **Non-suspicious domain pairs**.</span></span> <span data-ttu-id="ca09a-138">Эти категории далее делятся на три разных сегмента для просмотра.</span><span class="sxs-lookup"><span data-stu-id="ca09a-138">These categories are further subdivided into three different buckets for you to review.</span></span>

   <span data-ttu-id="ca09a-139">**Доменная** комбинация — это сочетание адреса "от" и инфраструктуры отправки:</span><span class="sxs-lookup"><span data-stu-id="ca09a-139">A **domain pair** is a combination of the From address and the sending infrastructure:</span></span>

   - <span data-ttu-id="ca09a-140">Адрес отправителя — это адрес электронной почты отправителя, который отображается в поле "от" в почтовых клиентах.</span><span class="sxs-lookup"><span data-stu-id="ca09a-140">The From address is the sender's email address that's displayed in the From box in email clients.</span></span> <span data-ttu-id="ca09a-141">Этот адрес также называется `5322.From` адресом.</span><span class="sxs-lookup"><span data-stu-id="ca09a-141">This address is also known as the `5322.From` address.</span></span>

   - <span data-ttu-id="ca09a-142">Отправляющей инфраструктурой или отправителем является организационным доменом обратного поиска DNS (записи PTR) отправляющего IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="ca09a-142">The sending infrastructure, or sender, is the organizational domain of the reverse DNS lookup (PTR record) of the sending IP address.</span></span> <span data-ttu-id="ca09a-143">Если у отправляющего IP-адреса нет записи PTR, отправитель идентифицируется с помощью отправляющего IP-адреса с маской подсети 255.255.255.0 в нотации CIDR (/24).</span><span class="sxs-lookup"><span data-stu-id="ca09a-143">If the sending IP address has no PTR record, then the sender is identified by the sending IP with the 255.255.255.0 subnet mask in CIDR notation (/24).</span></span> <span data-ttu-id="ca09a-144">Например, если IP-адрес 192.168.100.100, то полный IP-адрес отправителя — 192.168.100.100/24.</span><span class="sxs-lookup"><span data-stu-id="ca09a-144">For example, if the IP address is 192.168.100.100 then the complete IP address of the sender is 192.168.100.100/24.</span></span>

   <span data-ttu-id="ca09a-145">К **подозрительным парам доменов** относятся:</span><span class="sxs-lookup"><span data-stu-id="ca09a-145">**Suspicious domain pairs** include:</span></span>

   - <span data-ttu-id="ca09a-146">**Имитация высокой уверенности**: на основе шаблонов отправки с предысторией и оценки репутации доменов мы настоятельно уверены, что домены являются подменой, а сообщения из этих доменов скорее всего являются вредоносными.</span><span class="sxs-lookup"><span data-stu-id="ca09a-146">**High-confidence spoof**: Based on the historical sending patterns and the reputation score of the domains, we're highly confident that the domains are spoofing, and messages from these domains are more likely to be malicious.</span></span>

   - <span data-ttu-id="ca09a-147">**Подмена умеренной уверенности**: на основе прошлых шаблонов отправки и оценки репутации доменов мы умеренно уверены, что домены являются подложными и что сообщения, отправленные из этих доменов, являются законными.</span><span class="sxs-lookup"><span data-stu-id="ca09a-147">**Moderate confidence spoof**: Based on historical sending patterns and the reputation score of the domains, we're moderately confident that the domains are spoofing, and that messages sent from these domains are legitimate.</span></span> <span data-ttu-id="ca09a-148">Ложные срабатывания в этой категории более вероятнее, чем при подделке с высокой достоверностью.</span><span class="sxs-lookup"><span data-stu-id="ca09a-148">False positives are more likely in this category than high-confidence spoof.</span></span>

   - <span data-ttu-id="ca09a-149">**Пары доменов без подозрительных** сообщений (включает в себя **Аварийное подделку**): домену не удалось явно проверить подлинность проверки подлинности [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md)и [DMARC](use-dmarc-to-validate-email.md)).</span><span class="sxs-lookup"><span data-stu-id="ca09a-149">**Non-suspicious domain pairs** (includes **rescued spoof**): The domain failed explicit email authentication checks [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)).</span></span> <span data-ttu-id="ca09a-150">Однако домен передал неявную проверку подлинности электронной почты ([композитная проверка подлинности](email-validation-and-authentication.md#composite-authentication)).</span><span class="sxs-lookup"><span data-stu-id="ca09a-150">However, the domain passed our implicit email authentication checks ([composite authentication](email-validation-and-authentication.md#composite-authentication)).</span></span> <span data-ttu-id="ca09a-151">В результате этого сообщения не было выполнено никаких действий по защите от спуфинга.</span><span class="sxs-lookup"><span data-stu-id="ca09a-151">As a result, no anti-spoofing action was taken on the message.</span></span>

### <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a><span data-ttu-id="ca09a-152">Просмотр подробных сведений о подозрительных парах доменов из аналитической аналитики подделки</span><span class="sxs-lookup"><span data-stu-id="ca09a-152">View detailed information about suspicious domain pairs from the spoof intelligence insight</span></span>

1. <span data-ttu-id="ca09a-153">В поддельной информации выберите любую из пар доменов (высокая, средняя или копия).</span><span class="sxs-lookup"><span data-stu-id="ca09a-153">On the Spoof intelligence insight, click any of the domain pairs (high, moderate, or rescued).</span></span>

   <span data-ttu-id="ca09a-154">Откроется страница **аналитики подделки** .</span><span class="sxs-lookup"><span data-stu-id="ca09a-154">The **Spoof Intelligence insight** page appears.</span></span> <span data-ttu-id="ca09a-155">На странице отображается список отправителей, которые отправляют электронную почту, не прошедшие проверку подлинности, в вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="ca09a-155">The page shows you a list of senders who are sending unauthenticated email into your organization.</span></span>

   <span data-ttu-id="ca09a-156">Эта информация поможет определить, авторизованы ли поддельные сообщения, или необходимо предпринять дальнейшие действия.</span><span class="sxs-lookup"><span data-stu-id="ca09a-156">This information helps you determine whether spoofed messages are authorized, or if you need to take further action.</span></span>

   <span data-ttu-id="ca09a-157">Вы можете отсортировать информацию по количеству сообщений, дате и времени последнего обнаружения подделки и т. д.</span><span class="sxs-lookup"><span data-stu-id="ca09a-157">You can sort the information by message count, the date the spoof was last detected, and more.</span></span>

2. <span data-ttu-id="ca09a-158">Выберите элемент в таблице, чтобы открыть область сведений, в которой содержатся подробные сведения о данной учетной записи домена.</span><span class="sxs-lookup"><span data-stu-id="ca09a-158">Select an item in the table to open a details pane that contains rich information about the domain pair.</span></span> <span data-ttu-id="ca09a-159">Сведения включают:</span><span class="sxs-lookup"><span data-stu-id="ca09a-159">The information includes:</span></span>
   - <span data-ttu-id="ca09a-160">Почему мы перехватили это.</span><span class="sxs-lookup"><span data-stu-id="ca09a-160">Why we caught this.</span></span>
   - <span data-ttu-id="ca09a-161">Действия, которые необходимо выполнить.</span><span class="sxs-lookup"><span data-stu-id="ca09a-161">What you need to do.</span></span>
   - <span data-ttu-id="ca09a-162">Сводка по доменам.</span><span class="sxs-lookup"><span data-stu-id="ca09a-162">A domain summary.</span></span>
   - <span data-ttu-id="ca09a-163">Сведения о параметре WhoIs относительно отправителя.</span><span class="sxs-lookup"><span data-stu-id="ca09a-163">WhoIs data about the sender.</span></span>
   - <span data-ttu-id="ca09a-164">Похожие сообщения, которые мы видели в вашем клиенте, от того же отправителя.</span><span class="sxs-lookup"><span data-stu-id="ca09a-164">Similar messages we have seen in your tenant from the same sender.</span></span>

   <span data-ttu-id="ca09a-165">Отсюда вы можете добавить или удалить комбинацию домена из списка надежных отправителей **алловедтоспуф** .</span><span class="sxs-lookup"><span data-stu-id="ca09a-165">From here, you can also choose to add or remove the domain pair from the **AllowedToSpoof** safe sender list.</span></span>

   ![Снимок экрана с доменом в области подробных сведений о поддельной информации](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="add-or-remove-a-domain-from-the-allowedtospoof-list"></a><span data-ttu-id="ca09a-167">Добавление или удаление домена из списка Алловедтоспуф</span><span class="sxs-lookup"><span data-stu-id="ca09a-167">Add or remove a domain from the AllowedToSpoof list</span></span>

<span data-ttu-id="ca09a-168">Вы добавляете или удаляете домен из списка Алловедтоспуф ("надежный отправитель") в области сведений в области сведений о подделке для учетной зоны.</span><span class="sxs-lookup"><span data-stu-id="ca09a-168">You add or remove a domain from the AllowedToSpoof (safe sender) list in the details pane of the spoof intelligence insight for the domain pair.</span></span> <span data-ttu-id="ca09a-169">Просто установите переключатель соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="ca09a-169">Simply set the toggle accordingly.</span></span>

<span data-ttu-id="ca09a-170">Предоставление пары домена позволяет использовать только сочетание поддельного домена *и* инфраструктуры отправки.</span><span class="sxs-lookup"><span data-stu-id="ca09a-170">Allowing a domain pair only allows the combination of the spoofed domain *and* the sending infrastructure.</span></span> <span data-ttu-id="ca09a-171">Он не позволяет отправлять сообщения электронной почты от поддельного домена из любого источника, а также отправлять электронную почту из любой доменной инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="ca09a-171">It does not allow email from the spoofed domain from any source, nor does it allow email from the sending infrastructure for any domain.</span></span>

<span data-ttu-id="ca09a-172">Например, вы можете использовать следующую доменную комбинацию для отправки поддельных сообщений в организацию:</span><span class="sxs-lookup"><span data-stu-id="ca09a-172">For example, you allow the following domain pair to send spoofed messages into your organization:</span></span>

- <span data-ttu-id="ca09a-173">*Поддельный домен*: Gmail.com "</span><span class="sxs-lookup"><span data-stu-id="ca09a-173">*Spoofed Domain*: gmail.com"</span></span>
- <span data-ttu-id="ca09a-174">*Инфраструктура отправки* `tms.mx.com` :</span><span class="sxs-lookup"><span data-stu-id="ca09a-174">*Sending Infrastructure* `tms.mx.com`:</span></span>

<span data-ttu-id="ca09a-175">Только электронная почта из этой учетной области может быть разрешена для подмены.</span><span class="sxs-lookup"><span data-stu-id="ca09a-175">Only email from that domain pair will be allowed to spoof.</span></span> <span data-ttu-id="ca09a-176">Другие отправители, пытающиеся подменить gmail.com, не разрешены.</span><span class="sxs-lookup"><span data-stu-id="ca09a-176">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="ca09a-177">Сообщения в других доменах из tms.mx.com проверяются с помощью логики подделки.</span><span class="sxs-lookup"><span data-stu-id="ca09a-177">Messages in other domains from tms.mx.com are checked by spoof intelligence.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ca09a-178">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="ca09a-178">Related topics</span></span>

[<span data-ttu-id="ca09a-179">Защита от спуфинга в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ca09a-179">Anti-spoofing protection in Microsoft 365</span></span>](anti-spoofing-protection.md)
