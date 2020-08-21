---
title: Проверка подлинности электронной почты в Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- Strat_O365_IP
ms.custom: TopSMBIssues
localization_priority: Priority
description: Администраторы могут узнать об использовании проверки подлинности электронной почты (SPF, DKIM и DMARC) в Exchange Online Protection (EOP) для предотвращения спуфинга, фишинга и спама.
ms.openlocfilehash: cc9489a258608080118e88bf1375e4d5f35f8c77
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826653"
---
# <a name="email-authentication-in-eop"></a><span data-ttu-id="04fbb-103">Проверка подлинности электронной почты в EOP</span><span class="sxs-lookup"><span data-stu-id="04fbb-103">Email authentication in EOP</span></span>

<span data-ttu-id="04fbb-104">Проверка подлинности электронной почты (также известная как проверка адреса электронной почты) — это набор стандартов для борьбы со спуфингом (сообщения электронной почты от поддельных отправителей).</span><span class="sxs-lookup"><span data-stu-id="04fbb-104">Email authentication (also known as email validation) is a group of standards that tries to stop spoofing (email messages from forged senders).</span></span> <span data-ttu-id="04fbb-105">В организациях Microsoft 365 с почтовыми ящиками Exchange Online, а также в автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online применяются следующие стандарты для проверки входящей электронной почты с помощью EOP:</span><span class="sxs-lookup"><span data-stu-id="04fbb-105">In Microsoft 365 organizations with mailboxes in Exchange Online, and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses these standards to verify inbound email:</span></span>

- [<span data-ttu-id="04fbb-106">SPF</span><span class="sxs-lookup"><span data-stu-id="04fbb-106">SPF</span></span>](how-office-365-uses-spf-to-prevent-spoofing.md)

- [<span data-ttu-id="04fbb-107">DKIM</span><span class="sxs-lookup"><span data-stu-id="04fbb-107">DKIM</span></span>](support-for-validation-of-dkim-signed-messages.md)

- [<span data-ttu-id="04fbb-108">DMARC</span><span class="sxs-lookup"><span data-stu-id="04fbb-108">DMARC</span></span>](use-dmarc-to-validate-email.md)

<span data-ttu-id="04fbb-109">Проверка подлинности электронной почты удостоверяет, что письма отправителя (например, regina@contoso.com) являются подлинными и получены доменом электронной почты из ожидаемых источников (например, contoso.com)</span><span class="sxs-lookup"><span data-stu-id="04fbb-109">Email authentication verifies that email messages from a sender (for example, laura@contoso.com) are legitimate and come from expected sources for that email domain (for example, contoso.com.)</span></span>

<span data-ttu-id="04fbb-110">Далее в этой статье описываются принципы работы этих технологий, а также их использование службой EOP для проверки входящих писем.</span><span class="sxs-lookup"><span data-stu-id="04fbb-110">The rest of this topic explains how these technologies work, and how EOP uses them to check inbound email.</span></span>

## <a name="use-email-authentication-to-help-prevent-spoofing"></a><span data-ttu-id="04fbb-111">Использование проверки подлинности электронной почты для предотвращения спуфинга</span><span class="sxs-lookup"><span data-stu-id="04fbb-111">Use email authentication to help prevent spoofing</span></span>

<span data-ttu-id="04fbb-112">DMARC предотвращает спуфинг, анализируя адрес **отправителя** в сообщениях (адрес электронной почты отправителя, который пользователи видят в своих почтовых клиентах).</span><span class="sxs-lookup"><span data-stu-id="04fbb-112">DMARC prevents spoofing by examining the **From** address in messages (the sender email address that users see in their email client).</span></span> <span data-ttu-id="04fbb-113">Организации, которые получают электронную почту, также могут убедиться, что домен электронной почты прошел проверку SPF или DKIM, т. е. проверку подлинности, и угроза спуфинга отсутствует.</span><span class="sxs-lookup"><span data-stu-id="04fbb-113">Destination email organizations can also verify that the email domain has passed SPF or DKIM, which means that the domain has been authenticated and is therefore not spoofed.</span></span>

<span data-ttu-id="04fbb-114">Однако проблема заключается в том, что записи SPF, DKIM и DMARC в DNS для проверки подлинности электронной почты (известные под общим названием политик проверки подлинности электронной почты) не обязательны.</span><span class="sxs-lookup"><span data-stu-id="04fbb-114">However, the problem is that SPF, DKIM, and DMARC records in DNS for email authentication (collectively known as email authentication policies) are completely optional.</span></span> <span data-ttu-id="04fbb-115">Таким образом, хотя домены с надежными политиками проверки подлинности электронной почты, например, microsoft.com и skype.com, защищены от спуфинга, домены, которые используют менее надежные политики либо вообще не имеют никакой специальной политики, являются основной целью спуфинга.</span><span class="sxs-lookup"><span data-stu-id="04fbb-115">Therefore, while domains with strong email authentication policies like microsoft.com and skype.com are protected from spoofing, domains that publish weaker email authentication policies, or no policy at all, are prime targets for being spoofed.</span></span>

<span data-ttu-id="04fbb-116">В марте 2018 г. только 9 % доменов компаний из списка Fortune 500 публиковали надежные политики проверки подлинности электронной почты.</span><span class="sxs-lookup"><span data-stu-id="04fbb-116">As of March 2018, only 9% of domains of companies in the Fortune 500 publish strong email authentication policies.</span></span> <span data-ttu-id="04fbb-117">В остальных компаниях (91%) адреса могут быть подделаны злоумышленниками.</span><span class="sxs-lookup"><span data-stu-id="04fbb-117">The remaining 91% of companies might be spoofed by a attacker.</span></span> <span data-ttu-id="04fbb-118">Если не используется какой-либо другой механизм фильтрации электронной почты, сообщения от поддельных отправителей в этих доменах могут быть доставлены пользователям.</span><span class="sxs-lookup"><span data-stu-id="04fbb-118">Unless some other email filtering mechanism is in-place, email from spoofed senders in these domains might be delivered to users.</span></span>

![Политики DMARC компаний из списка Fortune 500](../../media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)

<span data-ttu-id="04fbb-120">Доля компаний малого и среднего бизнеса, не входящих в список Fortune 500, которые публикуют строгие политики проверки подлинности электронной почты, небольшая, и снижается для доменов электронной почты, которые находятся за пределами Северной Америки и Западной Европы.</span><span class="sxs-lookup"><span data-stu-id="04fbb-120">The proportion of small-to-medium sized companies that are not in the Fortune 500 that publish strong email authentication policies is smaller, and smaller still for email domains that are outside of North America and western Europe.</span></span>

<span data-ttu-id="04fbb-121">Это серьезная проблема, так как предприятие может не иметь четкого представления о том, как работает проверка подлинности электронной почты, в то время как злоумышленники отлично это знают и могут этим воспользоваться.</span><span class="sxs-lookup"><span data-stu-id="04fbb-121">This is a big problem because while enterprises may not be aware of how email authentication works, attackers fully understand and take advantage it.</span></span> <span data-ttu-id="04fbb-122">Так как фишинг является серьезной проблемой, а также из-за ограниченного внедрения политик проверки подлинности электронной почты, корпорация Майкрософт использует *неявную проверку подлинности* для проверки входящих писем.</span><span class="sxs-lookup"><span data-stu-id="04fbb-122">Because phishing is such a problem, and because of the limited adoption of strong email authentication policies, Microsoft uses *implicit email authentication* to check inbound email.</span></span>

<span data-ttu-id="04fbb-123">Неявная проверка подлинности проводится на основе многочисленных расширений для обычных политик проверки подлинности электронной почты.</span><span class="sxs-lookup"><span data-stu-id="04fbb-123">Implicit email authentication is built on numerous extensions to regular email authentication policies.</span></span> <span data-ttu-id="04fbb-124">Эти расширения включают репутацию отправителя, журнал отправителя, журнал получателя, анализ поведения и другие дополнительные методы.</span><span class="sxs-lookup"><span data-stu-id="04fbb-124">These extensions include sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques.</span></span> <span data-ttu-id="04fbb-125">Сообщение, отправленное с домена, который не использует политики проверки подлинности электронной почты, помечается как поддельное, если оно не содержит другие сигналы, подтверждающие его подлинность.</span><span class="sxs-lookup"><span data-stu-id="04fbb-125">A message sent from a domain that doesn't use email authentication policies will be marked as spoof unless it contains other signals to indicate that it's legitimate.</span></span>

<span data-ttu-id="04fbb-126">Общее извещение корпорации Майкрософт см. в статье [Море фишинга, часть 2 — Улучшенные средства борьбы со спуфингом в Microsoft 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).</span><span class="sxs-lookup"><span data-stu-id="04fbb-126">To see Microsoft's general announcement, see [A Sea of Phish Part 2 - Enhanced Anti-spoofing in Microsoft 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).</span></span>

## <a name="composite-authentication"></a><span data-ttu-id="04fbb-127">Многофакторная аутентификация</span><span class="sxs-lookup"><span data-stu-id="04fbb-127">Composite authentication</span></span>

<span data-ttu-id="04fbb-128">Хотя SPF, DKIM и DMARC полезны сами по себе, они не позволяют сообщить о достаточности проверки подлинности в случае, если в сообщении не содержится записей о явной проверке подлинности.</span><span class="sxs-lookup"><span data-stu-id="04fbb-128">While SPF, DKIM, and DMARC are all useful by themselves, they don't communicate enough authentication status in the event a message has no explicit authentication records.</span></span> <span data-ttu-id="04fbb-129">Поэтому корпорация Майкрософт разработала алгоритм неявной проверки подлинности, который объединяет несколько сигналов в одно значение, — _многофакторную аутентификацию_.</span><span class="sxs-lookup"><span data-stu-id="04fbb-129">Therefore, Microsoft has developed an algorithm for implicit email authentication that combines multiple signals into a single value called _composite authentication_, or compauth for short.</span></span> <span data-ttu-id="04fbb-130">Значение многофакторной аутентификации добавляется в заголовок **Authentication-Results** в заголовках сообщений.</span><span class="sxs-lookup"><span data-stu-id="04fbb-130">The compauth value is stamped into the **Authentication-Results** header in the message headers.</span></span>

> <span data-ttu-id="04fbb-131">Authentication-Results:</span><span class="sxs-lookup"><span data-stu-id="04fbb-131">Authentication-Results:</span></span><br/><span data-ttu-id="04fbb-132">&nbsp;&nbsp;&nbsp;compauth=\<fail | pass | softpass | none\> reason=\<yyy\></span><span class="sxs-lookup"><span data-stu-id="04fbb-132">&nbsp;&nbsp;&nbsp;compauth=\<fail | pass | softpass | none\> reason=\<yyy\></span></span>

<span data-ttu-id="04fbb-133">Эти значения описываются в разделе [Заголовок сообщения Authentication-results](anti-spam-message-headers.md#authentication-results-message-header).</span><span class="sxs-lookup"><span data-stu-id="04fbb-133">These values are explained at [Authentication-results message header](anti-spam-message-headers.md#authentication-results-message-header).</span></span>

<span data-ttu-id="04fbb-134">Изучив заголовки сообщений, администраторы и даже пользователи могут увидеть, каким образом Microsoft 365 определил, что отправитель поддельный.</span><span class="sxs-lookup"><span data-stu-id="04fbb-134">By examining the message headers, admins or even end users can determine how Microsoft 365 determined that the sender is spoofed.</span></span>

## <a name="why-email-authentication-is-not-always-enough-to-stop-spoofing"></a><span data-ttu-id="04fbb-135">Почему проверки подлинности электронной почты может быть недостаточно для борьбы со спуфингом</span><span class="sxs-lookup"><span data-stu-id="04fbb-135">Why email authentication is not always enough to stop spoofing</span></span>

<span data-ttu-id="04fbb-136">Использование только записей проверки подлинности электронной почты для определения, является ли входящее письмо поддельным, имеет следующие ограничения:</span><span class="sxs-lookup"><span data-stu-id="04fbb-136">Relying only on email authentication records to determine if an incoming message is spoofed has the following limitations:</span></span>

- <span data-ttu-id="04fbb-137">В отправляющем домене могут отсутствовать необходимые записи DNS, или же они могут быть неправильно настроены.</span><span class="sxs-lookup"><span data-stu-id="04fbb-137">The sending domain might lack the required DNS records, or the records are incorrectly configured.</span></span>

- <span data-ttu-id="04fbb-138">Записи DNS исходного домена настроены правильно, но он не совпадает с доменом в адресе отправителя.</span><span class="sxs-lookup"><span data-stu-id="04fbb-138">The source domain has correctly configured DNS records, but that domain doesn't match the domain in the From address.</span></span> <span data-ttu-id="04fbb-139">SPF и DKIM не требуют использовать домен в адресе отправителя.</span><span class="sxs-lookup"><span data-stu-id="04fbb-139">SPF and DKIM don't require the domain to be used in the From address.</span></span> <span data-ttu-id="04fbb-140">Злоумышленники или надежные службы могут зарегистрировать домен, настроить для него записи SPF и DKIM, использовать совершенно другой домен в адресе отправителя, и это сообщение пройдет проверку SPF и DKIM.</span><span class="sxs-lookup"><span data-stu-id="04fbb-140">Attackers or legitimate services can register a domain, configure SPF and DKIM for the domain, use a completely different domain in the From address, and that message will pass SPF and DKIM.</span></span>

<span data-ttu-id="04fbb-141">Многофакторная аутентификация позволяет устранить эти ограничения, пропуская сообщения, которые иначе не прошли бы проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="04fbb-141">Composite authentication can address these limitations by passing messages that would otherwise fail email authentication checks.</span></span>

> [!NOTE]
> <span data-ttu-id="04fbb-142">Как упоминалось выше, при неявной проверке подлинности используется несколько сигналов, чтобы определить, является ли сообщение подлинным.</span><span class="sxs-lookup"><span data-stu-id="04fbb-142">As described earlier, implicit email authentication uses multiple signals to determine if a message is legitimate.</span></span> <span data-ttu-id="04fbb-143">Для наглядности в приведенных ниже примерах рассматриваются результаты проверки подлинности электронной почты.</span><span class="sxs-lookup"><span data-stu-id="04fbb-143">For simplicity, the following examples concentrate on email authentication results.</span></span> <span data-ttu-id="04fbb-144">Другие интеллектуальные факторы серверной части могли определить сообщения, которые прошли проверку подлинности, как поддельные, а сообщения, которые не прошли проверку, как подлинные.</span><span class="sxs-lookup"><span data-stu-id="04fbb-144">Other back-end intelligence factors could identify messages that pass email authentication as spoofed, or messages that fail email email authentication as legitimate.</span></span>

<span data-ttu-id="04fbb-145">Например, для домена fabrikam.com записи SPF, DKIM или DMARC отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="04fbb-145">For example, the fabrikam.com domain has no SPF, DKIM, or DMARC records.</span></span> <span data-ttu-id="04fbb-146">Сообщения от отправителей в домене fabrikam.com могут не пройти многофакторную аутентификацию (обратите внимание на значение `compauth` и причину):</span><span class="sxs-lookup"><span data-stu-id="04fbb-146">Messages from senders in the fabrikam.com domain can fail composite authentication (note the `compauth` value and reason):</span></span>

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=fabrikam.com; compauth=fail reason=001
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="04fbb-147">Если fabrikam.com настраивает запись SPF и не настраивает DKIM, сообщение может пройти многофакторную аутентификацию, так как домен, прошедший проверку SPF, соответствует домену в адресе отправителя:</span><span class="sxs-lookup"><span data-stu-id="04fbb-147">If fabrikam.com configures an SPF without a DKIM record, the message can pass composite authentication, because the domain that passed SPF is aligned with the domain in the From address:</span></span>

```text
Authentication-Results: spf=pass (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="04fbb-148">Если fabrikam.com настраивает запись DKIM и не настраивает SPF, сообщение может пройти многофакторную аутентификацию, так как домен в подписи DKIM соответствует домену в адресе отправителя:</span><span class="sxs-lookup"><span data-stu-id="04fbb-148">If fabrikam.com configures a DKIM record without an SPF record, the message can pass composite authentication, because the domain in the passed DKIM signature is aligned with the domain in the From address:</span></span>

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.fabrikam.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="04fbb-149">Если домен в записи SPF или подписи DKIM не соответствует домену в адресе отправителя, сообщение может не пройти многофакторную аутентификацию.</span><span class="sxs-lookup"><span data-stu-id="04fbb-149">If the domain in SPF or the DKIM signature don't align with the domain in the From address, the message can fail composite authentication:</span></span>

```text
Authentication-Results: spf=none (sender IP is 192.168.1.8)
  smtp.mailfrom=maliciousdomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousdomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: chris@contoso.com
To: michelle@fabrikam.com
```

## <a name="solutions-for-legitimate-senders-who-are-sending-unauthenticated-email"></a><span data-ttu-id="04fbb-150">Решения для добросовестных отправителей, которые отправляют письма без проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="04fbb-150">Solutions for legitimate senders who are sending unauthenticated email</span></span>

<span data-ttu-id="04fbb-151">Microsoft 365 сохраняет сведения о том, кто отправляет непроверенную электронную почту вашей организации.</span><span class="sxs-lookup"><span data-stu-id="04fbb-151">Microsoft 365 keeps track of who is sending unauthenticated email to your organization.</span></span> <span data-ttu-id="04fbb-152">Если служба считает, что отправитель является ненадежным, она будет помечать почту как не прошедшую многофакторную аутентификацию.</span><span class="sxs-lookup"><span data-stu-id="04fbb-152">If the service thinks the sender is not legitimate, it will mark it as a composite authentication failure.</span></span> <span data-ttu-id="04fbb-153">Чтобы избежать этого, воспользуйтесь рекомендациями из этого раздела.</span><span class="sxs-lookup"><span data-stu-id="04fbb-153">To avoid this, you can use the recommendations in this section.</span></span>

### <a name="configure-email-authentication-for-domains-you-own"></a><span data-ttu-id="04fbb-154">Настройка проверки подлинности электронной почты для доменов, которыми вы владеете</span><span class="sxs-lookup"><span data-stu-id="04fbb-154">Configure email authentication for domains you own</span></span>

<span data-ttu-id="04fbb-155">Этот метод можно использовать для устранения спуфинга внутри организации, а также междоменного спуфинга, если вы владеете несколькими клиентами или взаимодействуете с ними.</span><span class="sxs-lookup"><span data-stu-id="04fbb-155">You can use this method to resolve intra-org spoofing and cross-domain spoofing in cases where you own or interact with multiple tenants.</span></span> <span data-ttu-id="04fbb-156">Он также позволяет устранить междоменный спуфинг, когда сообщения отправляются пользователям в среде Microsoft 365 или третьим сторонам, размещенным другими поставщиками.</span><span class="sxs-lookup"><span data-stu-id="04fbb-156">It also helps resolve cross-domain spoofing where you send to other customers within Microsoft 365 or third parties that are hosted by other providers.</span></span>

- <span data-ttu-id="04fbb-157">[Настройте записи SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md) для ваших доменов.</span><span class="sxs-lookup"><span data-stu-id="04fbb-157">[Configure SPF records](set-up-spf-in-office-365-to-help-prevent-spoofing.md) for your domains.</span></span>

- <span data-ttu-id="04fbb-158">[Настройте записи DKIM](use-dkim-to-validate-outbound-email.md) для ваших основных доменов.</span><span class="sxs-lookup"><span data-stu-id="04fbb-158">[Configure DKIM records](use-dkim-to-validate-outbound-email.md) for your primary domains.</span></span>

- <span data-ttu-id="04fbb-159">[Рекомендуем настроить записи DMARC ](use-dmarc-to-validate-email.md) для вашего домена, чтобы определить добросовестных отправителей.</span><span class="sxs-lookup"><span data-stu-id="04fbb-159">[Consider setting up DMARC records](use-dmarc-to-validate-email.md) for your domain to determine your legitimate senders.</span></span>

<span data-ttu-id="04fbb-160">Майкрософт не предоставляет подробные рекомендации по реализации для записей SPF, DKIM и DMARC.</span><span class="sxs-lookup"><span data-stu-id="04fbb-160">Microsoft doesn't provide detailed implementation guidelines for SPF, DKIM, and DMARC records.</span></span> <span data-ttu-id="04fbb-161">Однако большой объем информации доступен в Интернете.</span><span class="sxs-lookup"><span data-stu-id="04fbb-161">However, there's a lot of information available online.</span></span> <span data-ttu-id="04fbb-162">Существуют также сторонние компании, которые могут помочь вашей организации настроить записи для проверки подлинности электронной почты.</span><span class="sxs-lookup"><span data-stu-id="04fbb-162">There are also 3rd party companies dedicated to helping your organization set up email authentication records.</span></span>

#### <a name="you-dont-know-all-sources-for-your-email"></a><span data-ttu-id="04fbb-163">Вы не знаете все источники ваших писем</span><span class="sxs-lookup"><span data-stu-id="04fbb-163">You don't know all sources for your email</span></span>

<span data-ttu-id="04fbb-164">Многие домены не публикуют записи SPF, так как они не знают все источники сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="04fbb-164">Many domains don't publish SPF records because they don't know all of the email sources for messages in their domain.</span></span> <span data-ttu-id="04fbb-165">Начните с публикации записи SPF, содержащей все источники электронной почты, о которых вы знаете (особенно при наличии корпоративного трафика), и опубликуйте нейтральную политику SPF `?all`.</span><span class="sxs-lookup"><span data-stu-id="04fbb-165">Start by publishing an SPF record that contains all of the email sources you know about (especially where your corporate traffic is located), and publish the neutral SPF policy `?all`.</span></span> <span data-ttu-id="04fbb-166">Например:</span><span class="sxs-lookup"><span data-stu-id="04fbb-166">For example:</span></span>

```text
fabrikam.com IN TXT "v=spf1 include:spf.fabrikam.com ?all"
```

<span data-ttu-id="04fbb-167">Этот пример означает, что электронная почта из вашей корпоративной инфраструктуры пройдет проверку подлинности, а электронная почта из неизвестных источников будет возвращаться к нейтральному состоянию.</span><span class="sxs-lookup"><span data-stu-id="04fbb-167">This example means that email from your corporate infrastructure will pass email authentication, but email from unknown sources will fall back to neutral.</span></span>

<span data-ttu-id="04fbb-168">Microsoft 365 будет рассматривать входящие письма из вашей корпоративной инфраструктуры как прошедшие проверку подлинности, а письма из неизвестных источников могут быть помечены как поддельные (в зависимости от того, может ли Microsoft 365 выполнить неявную проверку подлинности).</span><span class="sxs-lookup"><span data-stu-id="04fbb-168">Microsoft 365 will treat inbound email from your corporate infrastructure as authenticated, but email from unidentified sources might still be marked as spoof (depending upon whether Microsoft 365 can implicitly authenticate it).</span></span> <span data-ttu-id="04fbb-169">Но это все равно является шагом вперед по сравнению с ситуацией, когда все электронные письма помечались как поддельные в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="04fbb-169">However, this is still an improvement from all email being marked as spoof by Microsoft 365.</span></span>

<span data-ttu-id="04fbb-170">Приступив к работе с политикой возврата SPF `?all`, вы можете постепенно найти и добавить больше источников для ваших сообщений, а затем обновить запись SPF с помощью более строгой политики.</span><span class="sxs-lookup"><span data-stu-id="04fbb-170">Once you've gotten started with an SPF fallback policy of `?all`, you can gradually discover and include more email sources for your messages, and then update your SPF record with a stricter policy.</span></span>

### <a name="use-spoof-intelligence-to-configure-permitted-senders-of-unauthenticated-email"></a><span data-ttu-id="04fbb-171">Использование аналитики спуфинга для настройки разрешенных отправителей непроверенной электронной почты</span><span class="sxs-lookup"><span data-stu-id="04fbb-171">Use spoof intelligence to configure permitted senders of unauthenticated email</span></span>

<span data-ttu-id="04fbb-172">Вы также можете использовать [аналитику спуфинга](learn-about-spoof-intelligence.md), чтобы предоставить отправителям разрешение на передачу непроверенных сообщений в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="04fbb-172">You can also use [spoof intelligence](learn-about-spoof-intelligence.md) to permit senders to transmit unauthenticated messages to your organization.</span></span>

<span data-ttu-id="04fbb-173">Для внешних доменов поддельный пользователь — это домен в адресе отправителя, а инфраструктура отправки — это либо исходный IP-адрес (разделенный на /24 диапазоны CIDR), либо домен организации в записи обратного поиска в DNS (запись типа PTR).</span><span class="sxs-lookup"><span data-stu-id="04fbb-173">For external domains, the spoofed user is the domain in the From address, while the sending infrastructure is either the source IP address (divided up into /24 CIDR ranges), or the organizational domain of the reverse DNS (PTR) record.</span></span>

<span data-ttu-id="04fbb-174">На снимке экрана, приведенном ниже, исходный IP-адрес — 131.107.18.4, с записью типа PTR outbound.mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="04fbb-174">In the screenshot below, the source IP might be 131.107.18.4 with the PTR record outbound.mail.protection.outlook.com.</span></span> <span data-ttu-id="04fbb-175">Она будет отображаться как outlook.com для инфраструктуры отправки.</span><span class="sxs-lookup"><span data-stu-id="04fbb-175">This would show up as outlook.com for the sending infrastructure.</span></span>

<span data-ttu-id="04fbb-176">Чтобы предоставить этому отправителю разрешение на отправку неавторизованной электронной почты, измените значение с **Нет** на **Да**.</span><span class="sxs-lookup"><span data-stu-id="04fbb-176">To permit this sender to send unauthenticated email, change the **No** to a **Yes**.</span></span>

![Настройка разрешенных отправителей для защиты от спуфинга](../../media/d4334921-d820-4334-8217-788279701e94.jpg)

### <a name="create-an-allow-entry-for-the-senderrecipient-pair"></a><span data-ttu-id="04fbb-178">Создание разрешающей записи для пары отправитель-получатель</span><span class="sxs-lookup"><span data-stu-id="04fbb-178">Create an allow entry for the sender/recipient pair</span></span>

<span data-ttu-id="04fbb-179">Чтобы обойти фильтрацию спама и некоторые компоненты фильтрации фишинга, но оставить фильтрацию вредоносных программ для определенных отправителей, см. статью [Создание списков надежных отправителей в Microsoft 365](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="04fbb-179">To bypass spam filtering, some parts of phish filtering, but not malware filtering for specific senders, see [Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span></span>

### <a name="ask-the-sender-to-configure-email-authentication-for-domains-you-dont-own"></a><span data-ttu-id="04fbb-180">Попросите отправителя настроить проверку подлинности электронной почты для доменов, которые вам не принадлежат</span><span class="sxs-lookup"><span data-stu-id="04fbb-180">Ask the sender to configure email authentication for domains you don't own</span></span>

<span data-ttu-id="04fbb-181">Из-за проблем со спамом и фишинговыми сообщениями корпорация Майкрософт рекомендует проверку подлинности электронной почты для всех организаций электронной почты.</span><span class="sxs-lookup"><span data-stu-id="04fbb-181">Because of the problem of spam and phishing, Microsoft recommends email authentication for all email organizations.</span></span> <span data-ttu-id="04fbb-182">Вместо настройки переопределения вручную в вашей организации вы можете попросить администратора в отправляющем домене настроить записи проверки подлинности электронной почты.</span><span class="sxs-lookup"><span data-stu-id="04fbb-182">Instead of configuring manual overrides in your organization, you can ask an admin in the sending domain to configure their email authentication records.</span></span>

- <span data-ttu-id="04fbb-183">Даже если им не нужно было публиковать записи проверки подлинности в прошлом, они придется сделать это сейчас, если они отправляют электронную почту в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="04fbb-183">Even if they didn't need to publish email authentication records in the past, they should do so if they send email to Microsoft.</span></span>

- <span data-ttu-id="04fbb-184">Настройте SPF для публикации IP-адреса отправителя для вашего домена, а также настройте DKIM (при наличии) для добавления цифровой подписи к сообщениям.</span><span class="sxs-lookup"><span data-stu-id="04fbb-184">Set up SPF to publish the domain's sending IP addresses, and set up DKIM (if available) to digitally sign messages.</span></span> <span data-ttu-id="04fbb-185">Кроме того, следует рассмотреть возможность настройки записей DMARC.</span><span class="sxs-lookup"><span data-stu-id="04fbb-185">They should also consider setting up DMARC records.</span></span>

- <span data-ttu-id="04fbb-186">Если они используют массовые рассылки для отправки электронной почты от их имени, убедитесь, что домен в адресе отправителя (если он принадлежит им) соответствует домену, который прошел проверку SPF или DMARC.</span><span class="sxs-lookup"><span data-stu-id="04fbb-186">If they use bulk senders to send email on their behalf, verify that the domain in the From address (if it belongs to them) aligns with the domain that passes SPF or DMARC.</span></span>

- <span data-ttu-id="04fbb-187">Убедитесь, что указанные ниже расположения (если они используют их) включены в запись SPF:</span><span class="sxs-lookup"><span data-stu-id="04fbb-187">Verify the following locations (if they use them) are included in the SPF record:</span></span>
  
  - <span data-ttu-id="04fbb-188">Локальные почтовые серверы.</span><span class="sxs-lookup"><span data-stu-id="04fbb-188">On-premises email servers.</span></span>
  - <span data-ttu-id="04fbb-189">Электронная почта, отправленная SaaS-поставщиком (программное обеспечение как услуга).</span><span class="sxs-lookup"><span data-stu-id="04fbb-189">Email sent from a software-as-a-service (SaaS) provider.</span></span>
  - <span data-ttu-id="04fbb-190">Электронная почта, отправленная службой размещения в облаке (Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services и т. д.).</span><span class="sxs-lookup"><span data-stu-id="04fbb-190">Email sent from a cloud-hosting service (Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services, etc.).</span></span>

- <span data-ttu-id="04fbb-191">Для небольших доменов, размещенных поставщиком услуг Интернета, настройте запись SPF согласно инструкциям поставщика.</span><span class="sxs-lookup"><span data-stu-id="04fbb-191">For small domains that are hosted by an ISP, configure the SPF record according to the instructions from the ISP.</span></span>

<span data-ttu-id="04fbb-192">Хотя сначала может показаться сложным заставить домены отправителя настроить проверку подлинности, но со временем, когда все новые и новые фильтры почты начнут отправлять в нежелательную почту или даже отклонять их почту, это заставит из настроить корректные записи для гарантии нормальной доставки почты.</span><span class="sxs-lookup"><span data-stu-id="04fbb-192">While it may be difficult at first to get sending domains to authenticate, over time, as more and more email filters start junking or even rejecting their email, it will cause them to set up the proper records to ensure better delivery.</span></span> <span data-ttu-id="04fbb-193">Кроме того, они могут помочь в борьбе с фишингом и снизить его вероятность в своей организации либо в организациях, которым они отправляют почту.</span><span class="sxs-lookup"><span data-stu-id="04fbb-193">Also, their participation can help in the fight against phishing, and can reduce the possibility of phishing in their organization or organizations that they send email to.</span></span>

#### <a name="information-for-infrastructure-providers-isps-esps-or-cloud-hosting-services"></a><span data-ttu-id="04fbb-194">Сведения для поставщиков инфраструктуры (поставщики услуг Интернета, ESP и службы размещения в облаке)</span><span class="sxs-lookup"><span data-stu-id="04fbb-194">Information for infrastructure providers (ISPs, ESPs, or cloud hosting services)</span></span>

<span data-ttu-id="04fbb-195">Если вы размещаете электронную почту для домена или предоставляете инфраструктуру для размещения, которая позволяет отправлять почту, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="04fbb-195">If you host a domain's email or provide hosting infrastructure that can send email, you should do the following steps:</span></span>

- <span data-ttu-id="04fbb-196">Убедитесь, что у ваших клиентов есть документация, в которой объясняется, как пользователи могут настраивать записи SPF.</span><span class="sxs-lookup"><span data-stu-id="04fbb-196">Ensure your customers have documentation that explains how your customers should configure their SPF records</span></span>

- <span data-ttu-id="04fbb-197">Рассмотрите возможность использования подписей DKIM для исходящих писем, даже если клиент не настроил эту опцию явным образом (подпись с доменом по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="04fbb-197">Consider signing DKIM-signatures on outbound email, even if the customer doesn't explicitly set it up (sign with a default domain).</span></span> <span data-ttu-id="04fbb-198">Вы можете даже дважды подписать электронную почту с помощью подписей DKIM (один раз с доменом клиента, если они настроили эту опцию, и еще раз с помощью подписи DKIM вашей организации)</span><span class="sxs-lookup"><span data-stu-id="04fbb-198">You can even double-sign the email with DKIM signatures (once with the customer's domain if they have set it up, and a second time with your company's DKIM signature)</span></span>

<span data-ttu-id="04fbb-199">Доставка в корпорацию Майкрософт не гарантируется, даже если пройдена проверка подлинности электронной почты, поступающей с вашей платформы, но, по крайней мере, вы можете быть уверены, что корпорация Майкрософт не будет направлять ваши письма в папку с нежелательными сообщения, которые не прошли проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="04fbb-199">Deliverability to Microsoft is not guaranteed even if you authenticate email originating from your platform, but at least it ensures that Microsoft does not junk your email because it isn't authenticated.</span></span>

<span data-ttu-id="04fbb-200">Дополнительные сведения о рекомендациях поставщиков услуг см. в статье [M3AAWG: Рекомендации по обмену мобильными сообщениями для поставщиков услуг](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf).</span><span class="sxs-lookup"><span data-stu-id="04fbb-200">For more details on service providers best practices, see [M3AAWG Mobile Messaging Best Practices for Service Providers](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf).</span></span>
