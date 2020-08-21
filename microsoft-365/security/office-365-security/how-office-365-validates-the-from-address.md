---
title: Как EOP проверяет адрес отправителя, чтобы предотвратить фишинг
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать о типах адресов электронной почты, которые приняты или отклоняются службой Exchange Online Protection и Outlook.com для предотвращения фишинга.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c67cf5855f2b0a99cf8d03bb6d7ba8557329b300
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827425"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="acd2b-103">Как EOP проверяет адрес отправителя, чтобы предотвратить фишинг</span><span class="sxs-lookup"><span data-stu-id="acd2b-103">How EOP validates the From address to prevent phishing</span></span>

<span data-ttu-id="acd2b-104">Фишинговые атаки — это постоянная угроза любой почтовой организации.</span><span class="sxs-lookup"><span data-stu-id="acd2b-104">Phishing attacks are a constant threat to any email organization.</span></span> <span data-ttu-id="acd2b-105">Помимо использования [поддельных (поддельных) электронных адресов отправителей](anti-spoofing-protection.md)злоумышленники часто используют значения в адресе отправителя, нарушающие стандарты Интернета.</span><span class="sxs-lookup"><span data-stu-id="acd2b-105">In addition to using [spoofed (forged) sender email addresses](anti-spoofing-protection.md), attackers often use values in the From address that violate internet standards.</span></span> <span data-ttu-id="acd2b-106">Чтобы предотвратить такой тип фишинга, в Exchange Online Protection (EOP) и Outlook.com входящие сообщения должны содержать соответствующий согласно Событию RFC-адрес отправителя, как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="acd2b-106">To help prevent this type of phishing, Exchange Online Protection (EOP) and Outlook.com now require inbound messages to include an RFC-compliant From address as described in this topic.</span></span> <span data-ttu-id="acd2b-107">Этот режим принудительного применения был включен в ноябре 2017 г.</span><span class="sxs-lookup"><span data-stu-id="acd2b-107">This enforcement was enabled in November 2017.</span></span>

<span data-ttu-id="acd2b-108">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="acd2b-108">**Notes**:</span></span>

- <span data-ttu-id="acd2b-109">Если вы регулярно получаете электронную почту от организаций, в которых неправильно сформированы адреса From, как описано в этом разделе, порекомендуйте организациям обновлять свои почтовые серверы в целях современных стандартов безопасности.</span><span class="sxs-lookup"><span data-stu-id="acd2b-109">If you regularly receive email from organizations that have malformed From addresses as described in this topic, encourage these organizations to update their email servers to comply with modern security standards.</span></span>

- <span data-ttu-id="acd2b-110">Эти требования не нарязываются на связанное поле "Отправитель" (используется на основе "Отправить от имени" и списками рассылки).</span><span class="sxs-lookup"><span data-stu-id="acd2b-110">The related Sender field (used by Send on Behalf and mailing lists) isn't affected by these requirements.</span></span> <span data-ttu-id="acd2b-111">Дополнительные сведения см. в записи блога, что означает, что это [означает, что мы ссылаемся на сообщение электронной почты?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)</span><span class="sxs-lookup"><span data-stu-id="acd2b-111">For more information, see the following blog post: [What do we mean when we refer to the 'sender' of an email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).</span></span>

## <a name="an-overview-of-email-message-standards"></a><span data-ttu-id="acd2b-112">Обзор стандартов электронных сообщений</span><span class="sxs-lookup"><span data-stu-id="acd2b-112">An overview of email message standards</span></span>

<span data-ttu-id="acd2b-113">Стандартное SMTP-сообщение электронной почты состоит из *конверта сообщения* и его содержимого.</span><span class="sxs-lookup"><span data-stu-id="acd2b-113">A standard SMTP email message consists of a *message envelope* and message content.</span></span> <span data-ttu-id="acd2b-114">Конверт сообщения содержит сведения, которые требуются для передачи и доставки сообщения между SMTP-серверами.</span><span class="sxs-lookup"><span data-stu-id="acd2b-114">The message envelope contains information that's required for transmitting and delivering the message between SMTP servers.</span></span> <span data-ttu-id="acd2b-115">Содержимое сообщения разделяется на поля заголовка сообщения, которые в совокупности называются *заголовком сообщения*, и текста сообщения.</span><span class="sxs-lookup"><span data-stu-id="acd2b-115">The message content contains message header fields (collectively called the *message header*) and the message body.</span></span> <span data-ttu-id="acd2b-116">Конверт сообщения описан в [документе RFC 5321,](https://tools.ietf.org/html/rfc5321)а заголовок сообщения в [документе RFC 5322.](https://tools.ietf.org/html/rfc5322)</span><span class="sxs-lookup"><span data-stu-id="acd2b-116">The message envelope is described in [RFC 5321](https://tools.ietf.org/html/rfc5321), and the message header is described in [RFC 5322](https://tools.ietf.org/html/rfc5322).</span></span> <span data-ttu-id="acd2b-117">Получатели не видят фактический конверт сообщения, так как он создается в процессе передачи сообщения и фактически не является частью самого сообщения.</span><span class="sxs-lookup"><span data-stu-id="acd2b-117">Recipients never see the actual message envelope because it's generated by the message transmission process, and it isn't actually part of the message.</span></span>

- <span data-ttu-id="acd2b-118">Адрес `5321.MailFrom` электронной почты (который также **называется адресом отправителя,** отправителем P1 или отправителем конверта) это адрес электронной почты, который используется при передаче сообщения.</span><span class="sxs-lookup"><span data-stu-id="acd2b-118">The `5321.MailFrom` address (also known as the **MAIL FROM** address, P1 sender, or envelope sender) is the email address that's used in the SMTP transmission of the message.</span></span> <span data-ttu-id="acd2b-119">Этот адрес, как правило, записывается в поле **заголовка сообщения Return-Path** (хотя отправитель может указать другой электронный адрес **Return-Path).**</span><span class="sxs-lookup"><span data-stu-id="acd2b-119">This email address is typically recorded in the **Return-Path** header field in the message header (although it's possible for the sender to designate a different **Return-Path** email address).</span></span>

- <span data-ttu-id="acd2b-120">`5322.From`(адрес отправителя" или "отправитель P2") это электронный адрес в поле **"От",** который отображается в почтовых клиентах.</span><span class="sxs-lookup"><span data-stu-id="acd2b-120">The `5322.From` (also known as the From address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span></span> <span data-ttu-id="acd2b-121">Адрес отправителя фокусируется на требованиях в этой теме.</span><span class="sxs-lookup"><span data-stu-id="acd2b-121">The From address is the focus of the requirements in this topic.</span></span>

<span data-ttu-id="acd2b-122">Адрес "От" подробно определяется в нескольких сферах RFC (например, разделы RFC 5322 3.2.3, 3.4 и 3.4.1 и [RFC 3696).](https://tools.ietf.org/html/rfc3696)</span><span class="sxs-lookup"><span data-stu-id="acd2b-122">The From address is defined in detail across several RFCs (for example, RFC 5322 sections 3.2.3, 3.4, and 3.4.1, and [RFC 3696](https://tools.ietf.org/html/rfc3696)).</span></span> <span data-ttu-id="acd2b-123">Существует много вариантов адресации, а также считается действительным или недействительным.</span><span class="sxs-lookup"><span data-stu-id="acd2b-123">There are many variations on addressing and what's considered valid or invalid.</span></span> <span data-ttu-id="acd2b-124">Для упрощения рекомендуется использовать следующий формат и определения:</span><span class="sxs-lookup"><span data-stu-id="acd2b-124">To keep it simple, we recommend the following format and definitions:</span></span>

`From: "Display Name" <EmailAddress>`

- <span data-ttu-id="acd2b-125">**Отображаемое имя**( необязательный фраза, описывающий владельца адреса электронной почты).</span><span class="sxs-lookup"><span data-stu-id="acd2b-125">**Display Name**: An optional phrase that describes the owner of the email address.</span></span>

  - <span data-ttu-id="acd2b-126">Мы рекомендуем всегда заключать отображаемое имя в двойные кавычки ("), как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="acd2b-126">We recommend that you always enclose the display name in double quotation marks (") as shown.</span></span> <span data-ttu-id="acd2b-127">Если отображаемое имя содержит запятую, _строку_ необходимо заключить в двойные кавычки на спецификации RFC 5322.</span><span class="sxs-lookup"><span data-stu-id="acd2b-127">If the display name contains a comma, you _must_ enclose the string in double quotation marks per RFC 5322.</span></span>
  - <span data-ttu-id="acd2b-128">Если адрес "От" содержит отображаемое имя, значение EmailAddress необходимо заключать в угловые скобки , < > как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="acd2b-128">If the From address includes a display name, the EmailAddress value must be enclosed in angle brackets (< >) as shown.</span></span>
  - <span data-ttu-id="acd2b-129">Корпорация Майкрософт настоятельно рекомендует вставить пробел между отображаемым именем и адресом электронной почты.</span><span class="sxs-lookup"><span data-stu-id="acd2b-129">Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>

- <span data-ttu-id="acd2b-130">**EmailAddress**: адрес электронной почты в следующем `local-part@domain` формате:</span><span class="sxs-lookup"><span data-stu-id="acd2b-130">**EmailAddress**: An email address uses the format `local-part@domain`:</span></span>

  - <span data-ttu-id="acd2b-131">**локальная часть:** строка, идентифицирующая почтовый ящик, связанный с адресом.</span><span class="sxs-lookup"><span data-stu-id="acd2b-131">**local-part**: A string that identifies the mailbox associated with the address.</span></span> <span data-ttu-id="acd2b-132">Это значение уникально для домена.</span><span class="sxs-lookup"><span data-stu-id="acd2b-132">This value is unique within the domain.</span></span> <span data-ttu-id="acd2b-133">Часто используется имя пользователя или GUID владельца почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="acd2b-133">Often, the mailbox owner's username or GUID is used.</span></span>
  - <span data-ttu-id="acd2b-134">**domain**(Полное доменное имя) сервера электронной почты, на котором размещается почтовый ящик, указанный локальной частью электронного адреса.</span><span class="sxs-lookup"><span data-stu-id="acd2b-134">**domain**: The fully qualified domain name (FQDN) of the email server that hosts the mailbox identified by the local-part of the email address.</span></span>

  <span data-ttu-id="acd2b-135">Ниже приведены некоторые дополнительные рекомендации для значения EmailAddress.</span><span class="sxs-lookup"><span data-stu-id="acd2b-135">These are some additional considerations for the EmailAddress value:</span></span>

  - <span data-ttu-id="acd2b-136">Только один адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="acd2b-136">Only one email address.</span></span>
  - <span data-ttu-id="acd2b-137">Рекомендуется не разделять угловые скобки пробелами.</span><span class="sxs-lookup"><span data-stu-id="acd2b-137">We recommend that you do not separate the angle brackets with spaces.</span></span>
  - <span data-ttu-id="acd2b-138">Не добавляйте дополнительные текстовые данные после адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="acd2b-138">Don't include additional text after the email address.</span></span>

## <a name="examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="acd2b-139">Примеры допустимых и недопустимых адресов From</span><span class="sxs-lookup"><span data-stu-id="acd2b-139">Examples of valid and invalid From addresses</span></span>

<span data-ttu-id="acd2b-140">Следующие адреса электронной почты полю являются допустимыми:</span><span class="sxs-lookup"><span data-stu-id="acd2b-140">The following From email addresses are valid:</span></span>

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- <span data-ttu-id="acd2b-141">`From: < sender@contoso.com >` (Не рекомендуется, так как между угловыми скобками и адресом электронной почты есть пробелы.)</span><span class="sxs-lookup"><span data-stu-id="acd2b-141">`From: < sender@contoso.com >` (Not recommended because there are spaces between the angle brackets and the email address.)</span></span>

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- <span data-ttu-id="acd2b-142">`From: Microsoft 365 <sender@contoso.com>` (Не рекомендуется, так как отображаемое имя не заключается в двойные кавычки.)</span><span class="sxs-lookup"><span data-stu-id="acd2b-142">`From: Microsoft 365 <sender@contoso.com>` (Not recommended because the display name is not enclosed in double quotation marks.)</span></span>

<span data-ttu-id="acd2b-143">Следующие адреса электронной почты недопустимы:</span><span class="sxs-lookup"><span data-stu-id="acd2b-143">The following From email addresses are invalid:</span></span>

- <span data-ttu-id="acd2b-144">**Адрес "Нет":** некоторые автоматические сообщения не включают адрес отправителя.</span><span class="sxs-lookup"><span data-stu-id="acd2b-144">**No From address**: Some automated messages don't include a From address.</span></span> <span data-ttu-id="acd2b-145">Ранее, когда Microsoft 365 или Outlook.com получает сообщение без адреса отправителя, служба добавила следующий адрес по умолчанию В: адрес, чтобы сделать сообщение доставленным.</span><span class="sxs-lookup"><span data-stu-id="acd2b-145">In the past, when Microsoft 365 or Outlook.com received a message without a From address, the service added the following default From: address to make the message deliverable:</span></span>

  `From: <>`

  <span data-ttu-id="acd2b-146">Теперь сообщения с пустым адресом "От" больше не принимаются.</span><span class="sxs-lookup"><span data-stu-id="acd2b-146">Now, messages with a blank From address are no longer accepted.</span></span>

- <span data-ttu-id="acd2b-147">`From: Microsoft 365 sender@contoso.com` (Отображаемое имя присутствует, но адрес электронной почты не заключается в угловые скобки.)</span><span class="sxs-lookup"><span data-stu-id="acd2b-147">`From: Microsoft 365 sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="acd2b-148">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Текст после адреса электронной почты.)</span><span class="sxs-lookup"><span data-stu-id="acd2b-148">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Text after the email address.)</span></span>

- <span data-ttu-id="acd2b-149">`From: Sender, Example <sender.example@contoso.com>` (Отображаемое имя содержит запятую, но не заключается в двойные кавычки.)</span><span class="sxs-lookup"><span data-stu-id="acd2b-149">`From: Sender, Example <sender.example@contoso.com>` (The display name contains a comma, but is not enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="acd2b-150">`From: "Microsoft 365 <sender@contoso.com>"` (Все значение неправильно заключено в двойные кавычки.)</span><span class="sxs-lookup"><span data-stu-id="acd2b-150">`From: "Microsoft 365 <sender@contoso.com>"` (The whole value is incorrectly enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="acd2b-151">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (Отображаемое имя присутствует, но адрес электронной почты не заключается в угловые скобки.)</span><span class="sxs-lookup"><span data-stu-id="acd2b-151">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="acd2b-152">`From: Microsoft 365<sender@contoso.com>` (Между отображаемым именем и левой угловой скобкой нет пробела.)</span><span class="sxs-lookup"><span data-stu-id="acd2b-152">`From: Microsoft 365<sender@contoso.com>` (No space between the display name and the left angle bracket.)</span></span>

- <span data-ttu-id="acd2b-153">`From: "Microsoft 365"<sender@contoso.com>` (Между закрывающей двойной кавычкой и левой угловой скобкой не должно быть пробела.)</span><span class="sxs-lookup"><span data-stu-id="acd2b-153">`From: "Microsoft 365"<sender@contoso.com>` (No space between the closing double quotation mark and the left angle bracket.)</span></span>

## <a name="suppress-auto-replies-to-your-custom-domain"></a><span data-ttu-id="acd2b-154">Запретить автоматические ответы на ваш пользовательский домен</span><span class="sxs-lookup"><span data-stu-id="acd2b-154">Suppress auto-replies to your custom domain</span></span>

<span data-ttu-id="acd2b-155">Это значение нельзя использовать `From: <>` для блокирования автоматических ответов.</span><span class="sxs-lookup"><span data-stu-id="acd2b-155">You can't use the value `From: <>` to suppress auto-replies.</span></span> <span data-ttu-id="acd2b-156">Вместо этого необходимо настроить пустую запись MX для личного домена.</span><span class="sxs-lookup"><span data-stu-id="acd2b-156">Instead, you need to set up a null MX record for your custom domain.</span></span> <span data-ttu-id="acd2b-157">Автоответчики (и все ответы) естественным образом блокируется, так как сервер ответящего сообщения может отправлять сообщения.</span><span class="sxs-lookup"><span data-stu-id="acd2b-157">Auto-replies (and all replies) are naturally suppressed because there is no published address that the responding server can send messages to.</span></span>

- <span data-ttu-id="acd2b-158">Выберите домен электронной почты, не получающий электронную почту.</span><span class="sxs-lookup"><span data-stu-id="acd2b-158">Choose an email domain that can't receive email.</span></span> <span data-ttu-id="acd2b-159">Например, если ваш основной домен contoso.com, можно выбрать noreply.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="acd2b-159">For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>

- <span data-ttu-id="acd2b-160">Нулевая запись MX для этого домена состоит из за один период.</span><span class="sxs-lookup"><span data-stu-id="acd2b-160">The null MX record for this domain consists of a single period.</span></span>

<span data-ttu-id="acd2b-161">Пример:</span><span class="sxs-lookup"><span data-stu-id="acd2b-161">For example:</span></span>

```text
noreply.contoso.com IN MX .
```

<span data-ttu-id="acd2b-162">Дополнительные сведения о настройке записей MX см. в статье Создание записей DNS для [Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)у любого поставщика услуг размещения DNS.</span><span class="sxs-lookup"><span data-stu-id="acd2b-162">For more information about setting up MX records, see [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

<span data-ttu-id="acd2b-163">Дополнительные сведения о публикации нулевого значения MX см. в [разделе RFC 7505.](https://tools.ietf.org/html/rfc7505)</span><span class="sxs-lookup"><span data-stu-id="acd2b-163">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>

## <a name="override-from-address-enforcement"></a><span data-ttu-id="acd2b-164">Переопределение адреса "От"</span><span class="sxs-lookup"><span data-stu-id="acd2b-164">Override From address enforcement</span></span>

<span data-ttu-id="acd2b-165">Чтобы обойти требования к адресу входящей почты, можно использовать список разрешенных IP-адресов (фильтрация подключений) или правила потока почты (также называемые правилами транспорта), как описано в [статье Создание списков надежных отправителей в Microsoft 365.](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="acd2b-165">To bypass the From address requirements for inbound email, you can use the IP Allow List (connection filtering) or mail flow rules (also known as transport rules) as described in [Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span></span>

<span data-ttu-id="acd2b-166">Переопределить требования к адресу отправителя для исходящей почты, отправляемой из Microsoft 365, невозможно.</span><span class="sxs-lookup"><span data-stu-id="acd2b-166">You can't override the From address requirements for outbound email that you send from Microsoft 365.</span></span> <span data-ttu-id="acd2b-167">Кроме того, Outlook.com не разрешает переопределения какого-либо типа даже через поддержку.</span><span class="sxs-lookup"><span data-stu-id="acd2b-167">In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span>

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a><span data-ttu-id="acd2b-168">Другие способы предотвращения киберпреступности и защиты от киберпресступности в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="acd2b-168">Other ways to prevent and protect against cybercrimes in Microsoft 365</span></span>

<span data-ttu-id="acd2b-169">Дополнительные сведения о том, как повысить защиту своей организации от фишинга, спама, нарушений безопасности данных и других угроз, см. в статье 10 основных [способов защиты планов Microsoft 365 для бизнеса.](../../admin/security-and-compliance/secure-your-business-data.md)</span><span class="sxs-lookup"><span data-stu-id="acd2b-169">For more information on how you can strengthen your organization against phishing, spam, data breaches, and other threats, see [Top 10 ways to secure Microsoft 365 for business plans](../../admin/security-and-compliance/secure-your-business-data.md).</span></span>
