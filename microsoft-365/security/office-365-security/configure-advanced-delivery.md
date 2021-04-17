---
title: Настройка доставки сторонних фишинговых симуляций пользователям и неотображемых сообщений в почтовые ящики SecOps
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: Администраторы могут узнать, как использовать передовую политику доставки в Exchange Online Protection (EOP) для определения сообщений, которые не должны фильтроваться в определенных поддерживаемых сценариях (сторонние имитации фишинга и сообщения, доставленные в почтовые ящики операций безопасности (SecOps).
ms.technology: mdo
ms.prod: m365-security
ROBOTS: NOINDEX
ms.openlocfilehash: 9d737472be5da2af0a0a36beb4b7914b8bfe3a10
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876069"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a><span data-ttu-id="7560e-103">Настройка доставки сторонних фишинговых симуляций пользователям и неотображемых сообщений в почтовые ящики SecOps</span><span class="sxs-lookup"><span data-stu-id="7560e-103">Configure the delivery of third-party phishing simulations to users and unfiltered messages to SecOps mailboxes</span></span>

<span data-ttu-id="7560e-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="7560e-104">**Applies to**</span></span>
- [<span data-ttu-id="7560e-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="7560e-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="7560e-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="7560e-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="7560e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7560e-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="7560e-108">Функция, описанная в этой статье, доступна не всем и подлежит изменениям.</span><span class="sxs-lookup"><span data-stu-id="7560e-108">The feature that's described in this article is in Preview, isn't available to everyone, and is subject to change.</span></span>

<span data-ttu-id="7560e-109">Чтобы обеспечить безопасность организации по [умолчанию,](secure-by-default.md)Exchange Online Protection (EOP) не разрешает безопасные списки или фильтрацию обхода для сообщений, которые привели к вредоносным программам или высокой уверенности в фишинговых решениях.</span><span class="sxs-lookup"><span data-stu-id="7560e-109">To keep your organization [secure by default](secure-by-default.md), Exchange Online Protection (EOP) does not allow safe lists or filtering bypass for messages that result in malware or high confidence phishing verdicts.</span></span> <span data-ttu-id="7560e-110">Но существуют определенные сценарии, которые требуют доставки неотобраченных сообщений.</span><span class="sxs-lookup"><span data-stu-id="7560e-110">But there are specific scenarios that require the delivery of unfiltered messages.</span></span> <span data-ttu-id="7560e-111">Например:</span><span class="sxs-lookup"><span data-stu-id="7560e-111">For example:</span></span>

- <span data-ttu-id="7560e-112">**Сторонние имитации фишинга.** Имитация атак может помочь вам идентифицировать уязвимых пользователей до того, как реальная атака ударит по организации.</span><span class="sxs-lookup"><span data-stu-id="7560e-112">**Third-party phishing simulations**: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="7560e-113">Почтовые ящики операций безопасности **(SecOps)**— выделенные почтовые ящики, используемые группами безопасности для сбора и анализа неотобраченных сообщений (как хороших, так и плохих).</span><span class="sxs-lookup"><span data-stu-id="7560e-113">**Security operations (SecOps) mailboxes**: Dedicated mailboxes that are used by security teams to collect and analyze unfiltered messages (both good and bad).</span></span>

<span data-ttu-id="7560e-114">Для _предотвращения_ фильтрации этих сообщений в этих конкретных  сценариях используется усовершенствованая политика доставки в Microsoft 365. <sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7560e-114">You use the _advanced delivery policy_ in Microsoft 365 to prevent these messages _in these specific scenarios_ from being filtered<sup>\*</sup>.</span></span> <span data-ttu-id="7560e-115">Усовершенствованая политика доставки гарантирует, что сообщения в этих сценариях не фильтруются:</span><span class="sxs-lookup"><span data-stu-id="7560e-115">The advanced delivery policy ensures that messages in these scenarios are not filtered:</span></span>

- <span data-ttu-id="7560e-116">Фильтры в EOP и Microsoft Defender для Office 365 не принимают никаких действий по этим сообщениям.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7560e-116">Filters in EOP and Microsoft Defender for Office 365 take no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="7560e-117">Очистка от нежелательной почты и фишинга с нулевой часовой очисткой [(ZAP)](zero-hour-auto-purge.md) не принимает никаких действий по этим сообщениям.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7560e-117">[Zero-hour Purge (ZAP)](zero-hour-auto-purge.md) for spam and phishing takes no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="7560e-118">[Для этих сценариев](alerts.md) системные оповещения по умолчанию не запускаются.</span><span class="sxs-lookup"><span data-stu-id="7560e-118">[Default system alerts](alerts.md) aren't triggered for these scenarios.</span></span>
- <span data-ttu-id="7560e-119">[Air и кластеризация в Defender для Office 365](office-365-air.md) игнорируют эти сообщения.</span><span class="sxs-lookup"><span data-stu-id="7560e-119">[AIR and clustering in Defender for Office 365](office-365-air.md) ignores these messages.</span></span>
- <span data-ttu-id="7560e-120">В частности, для сторонних имитаций фишинга:</span><span class="sxs-lookup"><span data-stu-id="7560e-120">Specifically for third-party phishing simulations:</span></span>
  - <span data-ttu-id="7560e-121">[Отправки администратора](admin-submission.md) создают автоматический ответ, который говорит, что сообщение является частью фишинговой кампании моделирования и не представляет реальной угрозы.</span><span class="sxs-lookup"><span data-stu-id="7560e-121">[Admin submissions](admin-submission.md) generates an automatic response saying that the message is part of a phishing simulation campaign and isn't a real threat.</span></span> <span data-ttu-id="7560e-122">Оповещения и AIR не будут запускаться.</span><span class="sxs-lookup"><span data-stu-id="7560e-122">Alerts and AIR will not be triggered.</span></span>
  - <span data-ttu-id="7560e-123">[Безопасные ссылки в Defender для Office 365](safe-links.md) не блокируют и не взрывают указанные URL-адреса в этих сообщениях.</span><span class="sxs-lookup"><span data-stu-id="7560e-123">[Safe Links in Defender for Office 365](safe-links.md) doesn't block or detonate the specifically identified URLs in these messages.</span></span>
  - <span data-ttu-id="7560e-124">[Безопасные вложения в Defender для Office 365](safe-attachments.md) не взрывают вложения в этих сообщениях.</span><span class="sxs-lookup"><span data-stu-id="7560e-124">[Safe Attachments in Defender for Office 365](safe-attachments.md) doesn't detonate attachments in these messages.</span></span>

<span data-ttu-id="7560e-125"><sup>\*</sup> Вы не можете обойти фильтрацию вредоносных программ или ZAP для вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="7560e-125"><sup>\*</sup> You can't bypass malware filtering or ZAP for malware.</span></span>

<span data-ttu-id="7560e-126">Сообщения, идентифицированные в продвинутой политике доставки, не являются угрозами безопасности, поэтому сообщения помечены как переопределения системы.</span><span class="sxs-lookup"><span data-stu-id="7560e-126">Messages that are identified by the advanced delivery policy aren't security threats, so the messages are marked as system overrides.</span></span> <span data-ttu-id="7560e-127">Администраторы могут фильтровать и анализировать эти переопределения системы в следующих интерфейсах:</span><span class="sxs-lookup"><span data-stu-id="7560e-127">Admins can filter and analyze these system overrides in the following experiences:</span></span>

- [<span data-ttu-id="7560e-128">Обнаружение обозревателя угроз и обнаружения в режиме реального времени в плане Defender для Office 365 2</span><span class="sxs-lookup"><span data-stu-id="7560e-128">Threat Explorer/Real-time detections in Defender for Office 365 plan 2</span></span>](threat-explorer.md)
- <span data-ttu-id="7560e-129">Страница [сущности электронной почты в обнаружении обозревателя угроз и обнаружения в режиме реального времени](mdo-email-entity-page.md)</span><span class="sxs-lookup"><span data-stu-id="7560e-129">The [Email entity Page in Threat Explorer/Real-time detections](mdo-email-entity-page.md)</span></span>
- <span data-ttu-id="7560e-130">Отчет [о состоянии защиты от угроз](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="7560e-130">The [Threat protection status report](view-email-security-reports.md#threat-protection-status-report)</span></span>
- [<span data-ttu-id="7560e-131">Расширенный поиск в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="7560e-131">Advanced hunting in Microsoft Defender for Endpoint</span></span>](../defender-endpoint/advanced-hunting-overview.md)
- [<span data-ttu-id="7560e-132">Представления кампании</span><span class="sxs-lookup"><span data-stu-id="7560e-132">Campaign Views</span></span>](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7560e-133">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="7560e-133">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7560e-134">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="7560e-134">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="7560e-135">Чтобы перейти непосредственно на **страницу advanced delivery,** откройте <https://protection.office.com/advanceddelivery> .</span><span class="sxs-lookup"><span data-stu-id="7560e-135">To go directly to the **Advanced delivery** page, open <https://protection.office.com/advanceddelivery>.</span></span>

- <span data-ttu-id="7560e-136">Прежде чем делать процедуры в этой статье, необходимо получить соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="7560e-136">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="7560e-137">Чтобы создать, изменить или удалить настроенные параметры в продвинутой политике доставки,  необходимо быть членом группы ролей администратора безопасности в  Центре обеспечения безопасности & соответствия требованиям и членом группы ролей управления организацией в **Exchange Online.** </span><span class="sxs-lookup"><span data-stu-id="7560e-137">To create, modify, or remove configured settings in the advanced delivery policy, you need to be a member of the **Security Administrator** role group in the **Security & Compliance Center** and a member of the **Organization Management** role group in **Exchange Online**.</span></span>  
  - <span data-ttu-id="7560e-138">Для доступа только для чтения к продвинутой политике доставки необходимо быть членом групп ролей **Global Reader** или **Security Reader.**</span><span class="sxs-lookup"><span data-stu-id="7560e-138">For read-only access to the advanced delivery policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="7560e-139">Дополнительные сведения см. [в веб-сайте Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online.](/exchange/permissions-exo/permissions-exo)</span><span class="sxs-lookup"><span data-stu-id="7560e-139">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

## <a name="use-the-security--compliance-center-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a><span data-ttu-id="7560e-140">Используйте Центр & безопасности для настройки сторонних имитаций фишинга в продвинутой политике доставки</span><span class="sxs-lookup"><span data-stu-id="7560e-140">Use the Security & Compliance Center to configure third-party phishing simulations in the advanced delivery policy</span></span>

1. <span data-ttu-id="7560e-141">В Центре обеспечения & безопасности перейдите к **службе advanced** delivery политики управления \>  \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="7560e-141">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="7560e-142">На странице **Advanced delivery** выберите вкладку **имитации фишинга** и нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="7560e-142">On the **Advanced delivery** page, select the **Phishing simulation** tab, and then click **Edit**.</span></span>

3. <span data-ttu-id="7560e-143">На **открываемой стороной** схеме фишинга настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="7560e-143">On the **Third-party phishing simulation** flyout that opens, configure the following settings:</span></span>

   - <span data-ttu-id="7560e-144">**Отправка** домена. Требуется по крайней мере один домен электронной почты (например, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="7560e-144">**Sending domain**: At least one email address domain is required (for example, contoso.com).</span></span> <span data-ttu-id="7560e-145">Можно добавить до 10 записей.</span><span class="sxs-lookup"><span data-stu-id="7560e-145">You can add up to 10 entries.</span></span>
   - <span data-ttu-id="7560e-146">**Отправка IP.** Требуется по крайней мере один допустимый адрес IPv4.</span><span class="sxs-lookup"><span data-stu-id="7560e-146">**Sending IP**: At least one valid IPv4 address is required.</span></span> <span data-ttu-id="7560e-147">Можно добавить до 10 записей.</span><span class="sxs-lookup"><span data-stu-id="7560e-147">You can add up to 10 entries.</span></span> <span data-ttu-id="7560e-148">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="7560e-148">Valid values are:</span></span>
     - <span data-ttu-id="7560e-149">Один IP. Например, 192.168.1.1.</span><span class="sxs-lookup"><span data-stu-id="7560e-149">Single IP: For example, 192.168.1.1.</span></span>
     - <span data-ttu-id="7560e-150">Диапазон IP: Например, 192.168.0.1-192.168.0.254.</span><span class="sxs-lookup"><span data-stu-id="7560e-150">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>
     - <span data-ttu-id="7560e-151">IP CIDR. Например, 192.168.0.1/25.</span><span class="sxs-lookup"><span data-stu-id="7560e-151">CIDR IP: For example, 192.168.0.1/25.</span></span>
   - <span data-ttu-id="7560e-152">**URL-адреса моделирования,** позволяющие: необязательно вводить определенные URL-адреса, которые являются частью вашей фишинговой кампании моделирования, которые не должны быть заблокированы или детонированы.</span><span class="sxs-lookup"><span data-stu-id="7560e-152">**Simulation URLs to allow**: Optionally, enter specific URLs that are part of your phishing simulation campaign that should not be blocked or detonated.</span></span> <span data-ttu-id="7560e-153">Можно добавить до 10 записей.</span><span class="sxs-lookup"><span data-stu-id="7560e-153">You can add up to 10 entries.</span></span>

4. <span data-ttu-id="7560e-154">По завершению нажмите кнопку **Сохранить.**</span><span class="sxs-lookup"><span data-stu-id="7560e-154">When you're finished, click **Save.**</span></span>

<span data-ttu-id="7560e-155">Настроенные сторонние записи моделирования фишинга отображаются на вкладке **Имитация** фишинга. Чтобы внести изменения, **нажмите кнопку Изменить** на вкладке.</span><span class="sxs-lookup"><span data-stu-id="7560e-155">The third-party phishing simulation entries that you configured are displayed on the **Phishing simulation** tab. To make changes, click **Edit** on the tab.</span></span>

## <a name="use-the-security--compliance-center-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a><span data-ttu-id="7560e-156">Используйте Центр & безопасности для настройки почтовых ящиков SecOps в продвинутой политике доставки</span><span class="sxs-lookup"><span data-stu-id="7560e-156">Use the Security & Compliance Center to configure SecOps mailboxes in the advanced delivery policy</span></span>

1. <span data-ttu-id="7560e-157">В Центре & безопасности перейдите к **службе advanced** delivery политики управления \>  \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="7560e-157">In the Security & Compliance Center, go to **Threat Management** \> **Policy** \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="7560e-158">На странице **Advanced delivery** выберите вкладку почтовый ящик **SecOps** и нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="7560e-158">On the **Advanced delivery** page, select the **SecOps mailbox** tab, and then click **Edit**.</span></span>

3. <span data-ttu-id="7560e-159">На открываемом флажке почтовых ящиков **SecOps** введите адреса электронной почты существующих почтовых ящиков Exchange Online, которые необходимо назначить почтовыми ящиками SecOps.</span><span class="sxs-lookup"><span data-stu-id="7560e-159">On the **SecOps mailbox** flyout that opens, enter the email addresses of existing Exchange Online mailboxes that you want to designate as SecOps mailboxes.</span></span> <span data-ttu-id="7560e-160">Группы рассылки запрещены.</span><span class="sxs-lookup"><span data-stu-id="7560e-160">Distribution groups are not allowed.</span></span>

4. <span data-ttu-id="7560e-161">Когда закончите, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7560e-161">When you're finished, click **Save**.</span></span>

<span data-ttu-id="7560e-162">Настроенные записи почтовых ящиков SecOps отображаются на вкладке **почтовый ящик SecOps.** Чтобы внести изменения, **нажмите кнопку Изменить** на вкладке.</span><span class="sxs-lookup"><span data-stu-id="7560e-162">The SecOps mailbox entries that you configured are displayed on the **SecOps mailbox** tab. To make changes, click **Edit** on the tab.</span></span>

## <a name="additional-scenarios-that-require-filtering-bypass"></a><span data-ttu-id="7560e-163">Дополнительные сценарии, которые требуют обхода фильтрации</span><span class="sxs-lookup"><span data-stu-id="7560e-163">Additional scenarios that require filtering bypass</span></span>

<span data-ttu-id="7560e-164">В дополнение к двум сценариям, которые может помочь вам усовершенствовать политика доставки, существуют и другие сценарии, которые могут потребовать обхода фильтрации:</span><span class="sxs-lookup"><span data-stu-id="7560e-164">In addition to the two scenarios that the advanced delivery policy can help you with, there are other scenarios that might require you bypass filtering:</span></span>

- <span data-ttu-id="7560e-165">**Сторонние фильтры.** Если запись MX  вашего домена не указывая на Office 365 (сообщения сначала будут отправляться в другом [месте),](secure-by-default.md) безопасность по умолчанию *недоступна.*</span><span class="sxs-lookup"><span data-stu-id="7560e-165">**Third-party filters**: If your domain's MX record *doesn't* point to Office 365 (messages are routed somewhere else first), [secure by default](secure-by-default.md) *is not available*.</span></span>

  <span data-ttu-id="7560e-166">Чтобы обойти фильтрацию microsoft для сообщений, уже оцененных сторонними фильтрами, используйте правила потока почты (также известные как правила транспорта), см. в рублях Использование правил потока почты для набора [SCL](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)в сообщениях.</span><span class="sxs-lookup"><span data-stu-id="7560e-166">To bypass Microsoft filtering for messages that have already been evaluated by third-party filtering, use mail flow rules (also known as transport rules), see [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

- <span data-ttu-id="7560e-167">**Ложные** срабатываки, которые рассматриваются в настоящее время. Вы [](admin-submission.md) можете временно разрешить некоторым сообщениям, которые по-прежнему анализируются Корпорацией Майкрософт с помощью представлений администратора, сообщать о известных хороших сообщениях, которые неправильно помечены как плохие для Microsoft (ложные срабатываки).</span><span class="sxs-lookup"><span data-stu-id="7560e-167">**False positives under review**: You might want to temporarily allow certain messages that are still being analyzed by Microsoft via [admin submissions](admin-submission.md) to report known good messages that are incorrectly being marked as bad to Microsoft (false positives).</span></span> <span data-ttu-id="7560e-168">Как и во всех переопределениях, настоятельно рекомендуется временно использовать эти надбавки. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="7560e-168">As with all overrides, it is **_highly recommended_** that these allowances be made temporarily.</span></span>
