---
title: Пошаговое руководство — результаты аналитики спуфинга
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать, как работает аналитика подмены. Они могут быстро определить, какие отправителей отправляют электронную почту в свои организации из доменов, которые не проходят проверку подлинности электронной почты (SPF, DKIM или DMARC).
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 91cd26498b2a14166f1be10921b9d5b2ea8d583c
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287975"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a><span data-ttu-id="27760-104">Walkthrough - Spoof intelligence insight in Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="27760-104">Walkthrough - Spoof intelligence insight in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="27760-105">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="27760-105">**Applies to**</span></span>
- [<span data-ttu-id="27760-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="27760-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="27760-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="27760-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="27760-108">В организациях Microsoft 365 с Защитником для Office 365 вы можете использовать аналитику спуфингов, чтобы быстро определить, какие внешние отправитые отправляют вам неавтериленную электронную почту (сообщения из доменов, которые не проходят проверки SPF, DKIM или DMARC).</span><span class="sxs-lookup"><span data-stu-id="27760-108">In Microsoft 365 organizations with Defender for Office 365, you can use the Spoof intelligence insight to quickly determine which external senders are legitimately sending you unauthenticated email (messages from domains that don't pass SPF, DKIM, or DMARC checks).</span></span>

<span data-ttu-id="27760-109">Разрешив известным внешним отправителям отправлять поддельные сообщения из известных мест, вы можете уменьшить количество ложных срабатывателей (хорошая почта помечена как неправижная).</span><span class="sxs-lookup"><span data-stu-id="27760-109">By allowing known external senders to send spoofed messages from known locations, you can reduce false positives (good email marked as bad).</span></span> <span data-ttu-id="27760-110">Отслеживая разрешенных поддельных отправителей, вы обеспечиваете дополнительный уровень безопасности, чтобы предотвратить отправку небезопасных сообщений в организацию.</span><span class="sxs-lookup"><span data-stu-id="27760-110">By monitoring the allowed spoofed senders, you provide an additional layer of security to prevent unsafe messages from arriving in your organization.</span></span>

<span data-ttu-id="27760-111">Дополнительные сведения об отчетах и статистике см. в отчетах и статистике в Центре [безопасности & соответствия требованиям.](reports-and-insights-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="27760-111">For more information about reports and insights, see [Reports and insights in the Security & Compliance Center](reports-and-insights-in-security-and-compliance.md).</span></span>

<span data-ttu-id="27760-112">Это по walkthrough is one of several for the Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="27760-112">This walkthrough is one of several for the Security & Compliance Center.</span></span> <span data-ttu-id="27760-113">Сведения о навигации по отчетам и сведениям см. в по walkthroughs in the [Related topics](#related-topics) section.</span><span class="sxs-lookup"><span data-stu-id="27760-113">To about navigating reports and insights, see the walkthroughs in the [Related topics](#related-topics) section.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="27760-114">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="27760-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="27760-115">Откройте Центр безопасности и соответствия требованиям по ссылке <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="27760-115">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="27760-116">Чтобы перейти непосредственно на **страницу панели мониторинга безопасности,** используйте <https://protection.office.com/searchandinvestigation/dashboard> .</span><span class="sxs-lookup"><span data-stu-id="27760-116">To go directly to the **Security dashboard** page, use <https://protection.office.com/searchandinvestigation/dashboard>.</span></span>

  <span data-ttu-id="27760-117">Аналитику спуфинга можно просмотреть на разных панелях мониторинга в Центре & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="27760-117">You can view the Spoof intelligence insight from more than one dashboard in the Security & Compliance Center.</span></span> <span data-ttu-id="27760-118">Независимо от того, какую панель мониторинга вы ищете, анализ предоставляет те же сведения и позволяет быстро выполнять те же задачи.</span><span class="sxs-lookup"><span data-stu-id="27760-118">Regardless of which dashboard you're looking at, the insight provides the same details and allows you to quickly do the same tasks.</span></span>

- <span data-ttu-id="27760-119">Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в Центре безопасности и соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="27760-119">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="27760-120">**Управление организацией**</span><span class="sxs-lookup"><span data-stu-id="27760-120">**Organization Management**</span></span>
  - <span data-ttu-id="27760-121">**Администратор безопасности**</span><span class="sxs-lookup"><span data-stu-id="27760-121">**Security Administrator**</span></span>
  - <span data-ttu-id="27760-122">**Читатель безопасности**</span><span class="sxs-lookup"><span data-stu-id="27760-122">**Security Reader**</span></span>
  - <span data-ttu-id="27760-123">**Глобальный читатель**</span><span class="sxs-lookup"><span data-stu-id="27760-123">**Global Reader**</span></span>

  <span data-ttu-id="27760-124">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="27760-124">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="27760-125">**Примечание.** Добавление пользователей к соответствующей роли Azure Active Directory в Центре администрирования Microsoft 365 предоставляет  пользователям необходимые разрешения в Центре безопасности и & соответствия требованиям и разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="27760-125">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="27760-126">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="27760-126">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="27760-127">Вы включаете и отключать аналитику спуфинга в политиках защиты от фишинга в Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="27760-127">You enable and disable spoof intelligence in anti-phishing policies in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="27760-128">Аналитика спуфингов включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="27760-128">Spoof intelligence is enabled by default.</span></span> <span data-ttu-id="27760-129">Дополнительные сведения см. в подстройке "Настройка политик защиты от фишинга" в [Microsoft Defender для Office 365.](configure-atp-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="27760-129">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="27760-130">Сведения о том, как использовать аналитику спуфингов для отслеживания отправителей, отправляющих вам непроверяемые сообщения, и управления ими, см. в подразмере "Настройка аналитики спуфинга" [в Microsoft 365.](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="27760-130">To use spoof intelligence to monitor and manage senders who are sending you unauthenticated messages, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a><span data-ttu-id="27760-131">Откройте аналитику подмены в Центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="27760-131">Open the spoof intelligence insight in the Security & Compliance Center</span></span>

1. <span data-ttu-id="27760-132">В Центре безопасности & соответствия требованиям перейдите на панель **мониторинга управления** \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="27760-132">In the Security & Compliance Center, go to **Threat Management** \> **Dashboard.**</span></span>

2. <span data-ttu-id="27760-133">В **строке "Insights"** найми один из следующих элементов:</span><span class="sxs-lookup"><span data-stu-id="27760-133">In the **Insights** row, look for one of the following items:</span></span>

   - <span data-ttu-id="27760-134">**Вероятные поддельные** домены за последние семь дней: это аналитика указывает, что аналитика спуфингов включена (она включена по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="27760-134">**Likely spoofed domains over the past seven days**: This insight indicates that spoof intelligence is enabled (it's enabled by default).</span></span>
   - <span data-ttu-id="27760-135">**Включайте защиту от** спуфинга: эта аналитика показывает, что аналитика спуфинга отключена, и щелчок по этой аналитике позволяет включить аналитику спуфинга.</span><span class="sxs-lookup"><span data-stu-id="27760-135">**Enable Spoof Protection**: This insight indicates that spoof intelligence is disabled, and clicking on the insight allows you to enable spoof intelligence.</span></span>

3. <span data-ttu-id="27760-136">В информационной панели показаны сведения, похожие на эти:</span><span class="sxs-lookup"><span data-stu-id="27760-136">The insight on the dashboard shows you information like this:</span></span>

   ![Снимок экрана: аналитика подмены](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   <span data-ttu-id="27760-138">Эта информация имеет два режима:</span><span class="sxs-lookup"><span data-stu-id="27760-138">This insight has two modes:</span></span>

   - <span data-ttu-id="27760-139">**Режим аналитики:** если включена аналитика спуфингов, анализ показывает количество сообщений, на которые повлияли возможности аналитики спуфингов за последние семь дней.</span><span class="sxs-lookup"><span data-stu-id="27760-139">**Insight mode**: If spoof intelligence is enabled, the insight shows you how many messages were impacted by our spoof intelligence capabilities over the past seven days.</span></span>
   - <span data-ttu-id="27760-140">**Что делать,** если режим : если аналитика спуфинг отключена, то в аналитике показано, сколько сообщений повлияет на наши возможности аналитики спуфингов за последние семь дней. </span><span class="sxs-lookup"><span data-stu-id="27760-140">**What if mode**: If spoof intelligence is disabled, then the insight shows you how many messages *would* have been impacted by our spoof intelligence capabilities over the past seven days.</span></span>

   <span data-ttu-id="27760-141">В любом случае поддельные домены, отображаемая в анализе, разделяются на две **категории:** подозрительные и не **подозрительные домены.**</span><span class="sxs-lookup"><span data-stu-id="27760-141">Either way, the spoofed domains displayed in the insight are separated into two categories: **Suspicious domains** and **Non-suspicious domains**.</span></span>

   - <span data-ttu-id="27760-142">**К подозрительным доменам** относятся:</span><span class="sxs-lookup"><span data-stu-id="27760-142">**Suspicious domains** include:</span></span>

     - <span data-ttu-id="27760-143">Спуфинг с высокой вероятностью: на основе исторических шаблонов отправки и репутации доменов мы с высокой вероятностью уверены, что домены спуфинг, а сообщения из этих доменов с большей вероятностью будут вредоносными.</span><span class="sxs-lookup"><span data-stu-id="27760-143">High-confidence spoof: Based on the historical sending patterns and the reputation score of the domains, we're highly confident that the domains are spoofing, and messages from these domains are more likely to be malicious.</span></span>

     - <span data-ttu-id="27760-144">Модерирующая достоверность подмены: на основе исторических шаблонов отправки и оценки репутации доменов мы в состоянии средней уверенности в том, что домены спуфинг и что сообщения, отправленные из этих доменов, являются подлинными.</span><span class="sxs-lookup"><span data-stu-id="27760-144">Moderate confidence spoof: Based on historical sending patterns and the reputation score of the domains, we're moderately confident that the domains are spoofing, and that messages sent from these domains are legitimate.</span></span> <span data-ttu-id="27760-145">Ложные срабатываия в этой категории более вероятны, чем спуфинг с высокой вероятностью.</span><span class="sxs-lookup"><span data-stu-id="27760-145">False positives are more likely in this category than high-confidence spoof.</span></span>

   <span data-ttu-id="27760-146">**Не подозрительные домены:** домену не удалось явным образом проверить подлинность электронной почты [SPF,](how-office-365-uses-spf-to-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)и [DMARC).](use-dmarc-to-validate-email.md)</span><span class="sxs-lookup"><span data-stu-id="27760-146">**Non-suspicious domains**: The domain failed explicit email authentication checks [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)).</span></span> <span data-ttu-id="27760-147">Тем не менее, домен прошел наши неявные проверки подлинности электронной почты[(составная проверка подлинности).](email-validation-and-authentication.md#composite-authentication)</span><span class="sxs-lookup"><span data-stu-id="27760-147">However, the domain passed our implicit email authentication checks ([composite authentication](email-validation-and-authentication.md#composite-authentication)).</span></span> <span data-ttu-id="27760-148">В результате к сообщению не было предприняты никаких действий по борьбе с спуфингом.</span><span class="sxs-lookup"><span data-stu-id="27760-148">As a result, no anti-spoofing action was taken on the message.</span></span>

### <a name="view-detailed-information-about-suspicious-domains-from-the-spoof-intelligence-insight"></a><span data-ttu-id="27760-149">Просмотр подробных сведений о подозрительных доменах из аналитики подмены</span><span class="sxs-lookup"><span data-stu-id="27760-149">View detailed information about suspicious domains from the Spoof intelligence insight</span></span>

1. <span data-ttu-id="27760-150">В аналитике спуфинга  щелкните "Подозрительные" или "Не **подозрительные"** домены, чтобы перейти на страницу аналитики подмены. </span><span class="sxs-lookup"><span data-stu-id="27760-150">On the Spoof intelligence insight, click **Suspicious domains** or **Non-suspicious domains** to go to the **Spoof intelligence insight** page.</span></span> <span data-ttu-id="27760-151">Страница **аналитики подмены** содержит следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="27760-151">The **Spoof Intelligence insight** page contains the following information:</span></span>

   - <span data-ttu-id="27760-152">**Поддельный домен**: домен подмены пользователя, который отображается в  поле "От" в почтовых клиентах.</span><span class="sxs-lookup"><span data-stu-id="27760-152">**Spoofed domain**: The domain of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="27760-153">Этот адрес также называется `5322.From` адресом.</span><span class="sxs-lookup"><span data-stu-id="27760-153">This address is also known as the `5322.From` address.</span></span>
   - <span data-ttu-id="27760-154">**Инфраструктура**: также известная как инфраструктура _отправки._</span><span class="sxs-lookup"><span data-stu-id="27760-154">**Infrastructure**: Also known as the _sending infrastructure_.</span></span> <span data-ttu-id="27760-155">Домен, найденный в обратном DNS-подыске (запись PTR) IP-адреса сервера электронной почты источника.</span><span class="sxs-lookup"><span data-stu-id="27760-155">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address.</span></span> <span data-ttu-id="27760-156">Если исходный IP-адрес не имеет записи PTR, инфраструктура отправки будет определена как \<source IP\> /24 (например, 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="27760-156">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>
   - <span data-ttu-id="27760-157">**Количество сообщений:** количество сообщений из инфраструктуры отправки в организацию, содержащих указанный поддельный домен за последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="27760-157">**Message count**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed domain within the last 7 days.</span></span>
   - <span data-ttu-id="27760-158">**Last seen**: the last date when a message was received from the sending infrastructure that contains the spoofed domain.</span><span class="sxs-lookup"><span data-stu-id="27760-158">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed domain.</span></span>
   - <span data-ttu-id="27760-159">**Тип подмены:** это значение **External**.</span><span class="sxs-lookup"><span data-stu-id="27760-159">**Spoof type**: This value is **External**.</span></span>
   - <span data-ttu-id="27760-160">**Разрешено спуфинг?**</span><span class="sxs-lookup"><span data-stu-id="27760-160">**Allowed to spoof?**: The values that you see here are:</span></span>
     - <span data-ttu-id="27760-161">**Да:** сообщения из комбинации подмены домена пользователя и инфраструктуры отправки разрешены и не рассматриваются как поддельные сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="27760-161">**Yes**: Messages from the combination of spoofed user's domain and sending infrastructure are allowed and not treated as spoofed email.</span></span>
     - <span data-ttu-id="27760-162">**Нет:** сообщения из комбинации подмены домена пользователя и инфраструктуры отправки помечаются как поддельные.</span><span class="sxs-lookup"><span data-stu-id="27760-162">**No**: Messages from the combination of spoofed user's domain and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="27760-163">Действие контролируется политикой защиты от фишинга по умолчанию или пользовательскими политиками защиты от фишинга (значение по умолчанию — Переместить сообщение в папку нежелательной **почты).**</span><span class="sxs-lookup"><span data-stu-id="27760-163">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span>

     <span data-ttu-id="27760-164">Дополнительные сведения см. в подстройке "Настройка политик защиты от фишинга" в [Microsoft Defender для Office 365.](configure-atp-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="27760-164">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

2. <span data-ttu-id="27760-165">Выберите элемент в списке, чтобы просмотреть сведения о паре инфраструктуры домен/отправляя во flyout.</span><span class="sxs-lookup"><span data-stu-id="27760-165">Select an item in the list to view details about the domain/sending infrastructure pair in a flyout.</span></span> <span data-ttu-id="27760-166">Эти сведения включают следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="27760-166">The information includes:</span></span>
   - <span data-ttu-id="27760-167">Почему мы перехвачены.</span><span class="sxs-lookup"><span data-stu-id="27760-167">Why we caught this.</span></span>
   - <span data-ttu-id="27760-168">Что нужно сделать.</span><span class="sxs-lookup"><span data-stu-id="27760-168">What you need to do.</span></span>
   - <span data-ttu-id="27760-169">Сводка по домену.</span><span class="sxs-lookup"><span data-stu-id="27760-169">A domain summary.</span></span>
   - <span data-ttu-id="27760-170">WhoIs data about the sender.</span><span class="sxs-lookup"><span data-stu-id="27760-170">WhoIs data about the sender.</span></span>
   - <span data-ttu-id="27760-171">Аналогичные сообщения, которые мы видели в клиенте от одного и того же отправителя.</span><span class="sxs-lookup"><span data-stu-id="27760-171">Similar messages we have seen in your tenant from the same sender.</span></span>

   <span data-ttu-id="27760-172">Здесь вы также можете добавить или удалить пару инфраструктуры "домен/отправитель" из списка разрешенных отправительов **"Разрешено** спуфинг".</span><span class="sxs-lookup"><span data-stu-id="27760-172">From here, you can also choose to add or remove the domain/sending infrastructure pair from the **Allowed to spoof** sender allow list.</span></span> <span data-ttu-id="27760-173">Просто установите его соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="27760-173">Simply set the toggle accordingly.</span></span>

   ![Снимок экрана: домен в области сведений аналитики подмены](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="adding-a-domain-to-the-allowed-to-spoof-list"></a><span data-ttu-id="27760-175">Добавление домена в список разрешенных для спуфингов</span><span class="sxs-lookup"><span data-stu-id="27760-175">Adding a domain to the Allowed to spoof list</span></span>

<span data-ttu-id="27760-176">Добавление домена в список разрешенных для спуфингов из аналитики спуфинга позволяет использовать только подмену домена и *инфраструктуру* отправки.</span><span class="sxs-lookup"><span data-stu-id="27760-176">Adding a domain to the Allowed to spoof list from the spoof intelligence insight only allows the combination of the spoofed domain *and* the sending infrastructure.</span></span> <span data-ttu-id="27760-177">Он не разрешает электронную почту из подмены домена из любого источника и не разрешает электронную почту из инфраструктуры отправки для какого-либо домена.</span><span class="sxs-lookup"><span data-stu-id="27760-177">It does not allow email from the spoofed domain from any source, nor does it allow email from the sending infrastructure for any domain.</span></span>

<span data-ttu-id="27760-178">Например, вы разрешаете следующий домен в списке разрешенных для спуфингов:</span><span class="sxs-lookup"><span data-stu-id="27760-178">For example, you allow the following domain to the Allowed to spoof list:</span></span>

- <span data-ttu-id="27760-179">**Домен**: gmail.com</span><span class="sxs-lookup"><span data-stu-id="27760-179">**Domain**: gmail.com</span></span>
- <span data-ttu-id="27760-180">**Инфраструктура**: tms.mx.com</span><span class="sxs-lookup"><span data-stu-id="27760-180">**Infrastructure**: tms.mx.com</span></span>

<span data-ttu-id="27760-181">Подмена будет разрешена только электронной почте из этой пары инфраструктуры домена и отправляя.</span><span class="sxs-lookup"><span data-stu-id="27760-181">Only email from that domain/sending infrastructure pair will be allowed to spoof.</span></span> <span data-ttu-id="27760-182">Другие отправитые, пытающиеся gmail.com подмену, не допускаются.</span><span class="sxs-lookup"><span data-stu-id="27760-182">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="27760-183">Сообщения в других доменах из tms.mx.com проверяются с помощью аналитики спуфинга.</span><span class="sxs-lookup"><span data-stu-id="27760-183">Messages in other domains from tms.mx.com are checked by spoof intelligence.</span></span>

## <a name="related-topics"></a><span data-ttu-id="27760-184">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="27760-184">Related topics</span></span>

[<span data-ttu-id="27760-185">Защита от спуфинга в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="27760-185">Anti-spoofing protection in Microsoft 365</span></span>](anti-spoofing-protection.md)
