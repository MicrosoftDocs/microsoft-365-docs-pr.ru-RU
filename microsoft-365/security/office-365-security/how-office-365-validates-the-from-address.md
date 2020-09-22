---
title: Как EOP проверяет адрес отправителя для предотвращения фишинга
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
description: Администраторы могут узнать о типах адресов электронной почты, которые принимаются или отклоняются службой Exchange Online Protection (EOP) и Outlook.com, чтобы помочь предотвратить фишинг.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e0afd05c80bb4de665d23b17c7089631dad93c78
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196063"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="35a32-103">Как EOP проверяет адрес отправителя для предотвращения фишинга</span><span class="sxs-lookup"><span data-stu-id="35a32-103">How EOP validates the From address to prevent phishing</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="35a32-104">Фишинговая атака — это постоянная угроза для любой организации электронной почты.</span><span class="sxs-lookup"><span data-stu-id="35a32-104">Phishing attacks are a constant threat to any email organization.</span></span> <span data-ttu-id="35a32-105">В дополнение к использованию [поддельных адресов электронной почты отправителя](anti-spoofing-protection.md), злоумышленники часто используют значения из адреса "от", которые нарушают стандарты Интернета.</span><span class="sxs-lookup"><span data-stu-id="35a32-105">In addition to using [spoofed (forged) sender email addresses](anti-spoofing-protection.md), attackers often use values in the From address that violate internet standards.</span></span> <span data-ttu-id="35a32-106">Чтобы предотвратить такой тип фишинга, для Exchange Online Protection (EOP) и Outlook.com теперь необходимо, чтобы входящие сообщения включали адрес, соответствующий спецификации RFC, как описано в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="35a32-106">To help prevent this type of phishing, Exchange Online Protection (EOP) and Outlook.com now require inbound messages to include an RFC-compliant From address as described in this topic.</span></span> <span data-ttu-id="35a32-107">Это принудительное применение было включено в ноябре 2017 ноября.</span><span class="sxs-lookup"><span data-stu-id="35a32-107">This enforcement was enabled in November 2017.</span></span>

<span data-ttu-id="35a32-108">**Примечания.**</span><span class="sxs-lookup"><span data-stu-id="35a32-108">**Notes**:</span></span>

- <span data-ttu-id="35a32-109">Если вы регулярно получаете электронную почту из организаций с неправильными адресами, как описано в этом разделе, рекомендуется, чтобы эти организации обновляли свои почтовые серверы, чтобы соответствовать современным стандартам безопасности.</span><span class="sxs-lookup"><span data-stu-id="35a32-109">If you regularly receive email from organizations that have malformed From addresses as described in this topic, encourage these organizations to update their email servers to comply with modern security standards.</span></span>

- <span data-ttu-id="35a32-110">Соответствующие поля отправителя (которые используются в списках отправки от имени и корреспонденции) не зависят от этих требований.</span><span class="sxs-lookup"><span data-stu-id="35a32-110">The related Sender field (used by Send on Behalf and mailing lists) isn't affected by these requirements.</span></span> <span data-ttu-id="35a32-111">Для получения дополнительных сведений ознакомьтесь со следующей записью блога: [что означает, что мы указываем, как ссылку на отправителя электронного сообщения?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).</span><span class="sxs-lookup"><span data-stu-id="35a32-111">For more information, see the following blog post: [What do we mean when we refer to the 'sender' of an email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).</span></span>

## <a name="an-overview-of-email-message-standards"></a><span data-ttu-id="35a32-112">Обзор стандартов сообщений электронной почты</span><span class="sxs-lookup"><span data-stu-id="35a32-112">An overview of email message standards</span></span>

<span data-ttu-id="35a32-113">Стандартное SMTP-сообщение электронной почты состоит из *конверта сообщения* и его содержимого.</span><span class="sxs-lookup"><span data-stu-id="35a32-113">A standard SMTP email message consists of a *message envelope* and message content.</span></span> <span data-ttu-id="35a32-114">Конверт сообщения содержит сведения, необходимые для передачи и доставки сообщения между SMTP-серверами.</span><span class="sxs-lookup"><span data-stu-id="35a32-114">The message envelope contains information that's required for transmitting and delivering the message between SMTP servers.</span></span> <span data-ttu-id="35a32-115">Содержимое сообщения разделяется на поля заголовка сообщения, которые в совокупности называются *заголовком сообщения*, и текста сообщения.</span><span class="sxs-lookup"><span data-stu-id="35a32-115">The message content contains message header fields (collectively called the *message header*) and the message body.</span></span> <span data-ttu-id="35a32-116">Конверт сообщения описан в [rfc 5321](https://tools.ietf.org/html/rfc5321), а заголовок сообщения описан в [RFC 5322](https://tools.ietf.org/html/rfc5322).</span><span class="sxs-lookup"><span data-stu-id="35a32-116">The message envelope is described in [RFC 5321](https://tools.ietf.org/html/rfc5321), and the message header is described in [RFC 5322](https://tools.ietf.org/html/rfc5322).</span></span> <span data-ttu-id="35a32-117">Получатели не видят собственно конверт сообщения, так как он создается процессом передачи сообщений, и фактически не является частью сообщения.</span><span class="sxs-lookup"><span data-stu-id="35a32-117">Recipients never see the actual message envelope because it's generated by the message transmission process, and it isn't actually part of the message.</span></span>

- <span data-ttu-id="35a32-118">`5321.MailFrom`Адрес электронной почты, который используется для передачи сообщения по протоколу SMTP, — это адрес электронной почты, который также называется адресом **электронной почты** , отправителями и отправителями конвертов.</span><span class="sxs-lookup"><span data-stu-id="35a32-118">The `5321.MailFrom` address (also known as the **MAIL FROM** address, P1 sender, or envelope sender) is the email address that's used in the SMTP transmission of the message.</span></span> <span data-ttu-id="35a32-119">Этот адрес электронной почты обычно записывается в поле заголовка " **Возврат-путь** " в заголовке сообщения (хотя можно указать другой адрес электронной почты для **получения пути** ).</span><span class="sxs-lookup"><span data-stu-id="35a32-119">This email address is typically recorded in the **Return-Path** header field in the message header (although it's possible for the sender to designate a different **Return-Path** email address).</span></span>

- <span data-ttu-id="35a32-120">`5322.From`(Другое название — "адрес отправителя" или "отправитель P2") — это адрес электронной почты в поле заголовка " **от** ", а это адрес электронной почты отправителя, отображаемый в почтовых клиентах.</span><span class="sxs-lookup"><span data-stu-id="35a32-120">The `5322.From` (also known as the From address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span></span> <span data-ttu-id="35a32-121">Адрес отправителя является участником требований, описанных в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="35a32-121">The From address is the focus of the requirements in this topic.</span></span>

<span data-ttu-id="35a32-122">Адрес отправителя определяется в нескольких документах RFC (например, в разделах RFC 5322, 3.2.3, 3,4 и 3.4.1, а также [rfc 3696](https://tools.ietf.org/html/rfc3696)).</span><span class="sxs-lookup"><span data-stu-id="35a32-122">The From address is defined in detail across several RFCs (for example, RFC 5322 sections 3.2.3, 3.4, and 3.4.1, and [RFC 3696](https://tools.ietf.org/html/rfc3696)).</span></span> <span data-ttu-id="35a32-123">Существует множество вариантов адресации, что считается допустимым или недопустимым.</span><span class="sxs-lookup"><span data-stu-id="35a32-123">There are many variations on addressing and what's considered valid or invalid.</span></span> <span data-ttu-id="35a32-124">Для простоты рекомендуется использовать следующий формат и определения:</span><span class="sxs-lookup"><span data-stu-id="35a32-124">To keep it simple, we recommend the following format and definitions:</span></span>

`From: "Display Name" <EmailAddress>`

- <span data-ttu-id="35a32-125">**Отображаемое имя**: необязательная фраза, описывающая владельца адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="35a32-125">**Display Name**: An optional phrase that describes the owner of the email address.</span></span>

  - <span data-ttu-id="35a32-126">Рекомендуется всегда заключать отображаемое имя в двойные кавычки ("), как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="35a32-126">We recommend that you always enclose the display name in double quotation marks (") as shown.</span></span> <span data-ttu-id="35a32-127">Если отображаемое имя содержит запятую, эту строку _необходимо_ заключить в двойные кавычки в RFC 5322.</span><span class="sxs-lookup"><span data-stu-id="35a32-127">If the display name contains a comma, you _must_ enclose the string in double quotation marks per RFC 5322.</span></span>
  - <span data-ttu-id="35a32-128">Если адрес отправителя содержит отображаемое имя, значение EmailAddress необходимо заключить в угловые скобки (< >), как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="35a32-128">If the From address includes a display name, the EmailAddress value must be enclosed in angle brackets (< >) as shown.</span></span>
  - <span data-ttu-id="35a32-129">Корпорация Майкрософт настоятельно рекомендует вставлять пробел между отображаемым именем и адресом электронной почты.</span><span class="sxs-lookup"><span data-stu-id="35a32-129">Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>

- <span data-ttu-id="35a32-130">**EmailAddress**: адрес электронной почты использует следующий формат `local-part@domain` :</span><span class="sxs-lookup"><span data-stu-id="35a32-130">**EmailAddress**: An email address uses the format `local-part@domain`:</span></span>

  - <span data-ttu-id="35a32-131">**Локальная часть**: строка, которая определяет почтовый ящик, связанный с адресом.</span><span class="sxs-lookup"><span data-stu-id="35a32-131">**local-part**: A string that identifies the mailbox associated with the address.</span></span> <span data-ttu-id="35a32-132">Это значение уникально в пределах домена.</span><span class="sxs-lookup"><span data-stu-id="35a32-132">This value is unique within the domain.</span></span> <span data-ttu-id="35a32-133">Часто используется имя пользователя или идентификатор GUID владельца почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="35a32-133">Often, the mailbox owner's username or GUID is used.</span></span>
  - <span data-ttu-id="35a32-134">**домен**: полное доменное имя (FQDN) сервера электронной почты, на котором размещается почтовый ящик, определенный локальной частью адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="35a32-134">**domain**: The fully qualified domain name (FQDN) of the email server that hosts the mailbox identified by the local-part of the email address.</span></span>

  <span data-ttu-id="35a32-135">Ниже приведены некоторые дополнительные рекомендации по значению EmailAddress:</span><span class="sxs-lookup"><span data-stu-id="35a32-135">These are some additional considerations for the EmailAddress value:</span></span>

  - <span data-ttu-id="35a32-136">Только один адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="35a32-136">Only one email address.</span></span>
  - <span data-ttu-id="35a32-137">Мы не рекомендуем разделять угловые скобки пробелами.</span><span class="sxs-lookup"><span data-stu-id="35a32-137">We recommend that you do not separate the angle brackets with spaces.</span></span>
  - <span data-ttu-id="35a32-138">Не включайте дополнительный текст после адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="35a32-138">Don't include additional text after the email address.</span></span>

## <a name="examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="35a32-139">Примеры допустимых и недопустимых адресов для адресов</span><span class="sxs-lookup"><span data-stu-id="35a32-139">Examples of valid and invalid From addresses</span></span>

<span data-ttu-id="35a32-140">Следующие адреса электронной почты являются допустимыми:</span><span class="sxs-lookup"><span data-stu-id="35a32-140">The following From email addresses are valid:</span></span>

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- <span data-ttu-id="35a32-141">`From: < sender@contoso.com >` (Не рекомендуется, так как между угловыми скобками и адресом электронной почты есть пробелы).</span><span class="sxs-lookup"><span data-stu-id="35a32-141">`From: < sender@contoso.com >` (Not recommended because there are spaces between the angle brackets and the email address.)</span></span>

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- <span data-ttu-id="35a32-142">`From: Microsoft 365 <sender@contoso.com>` (Не рекомендуется, так как отображаемое имя не заключено в двойные кавычки).</span><span class="sxs-lookup"><span data-stu-id="35a32-142">`From: Microsoft 365 <sender@contoso.com>` (Not recommended because the display name is not enclosed in double quotation marks.)</span></span>

<span data-ttu-id="35a32-143">Следующие адреса электронной почты являются недопустимыми:</span><span class="sxs-lookup"><span data-stu-id="35a32-143">The following From email addresses are invalid:</span></span>

- <span data-ttu-id="35a32-144">**Нет адреса**: некоторые автоматические сообщения не включают адрес отправителя.</span><span class="sxs-lookup"><span data-stu-id="35a32-144">**No From address**: Some automated messages don't include a From address.</span></span> <span data-ttu-id="35a32-145">В прошлое, когда Microsoft 365 или Outlook.com получил сообщение без адреса отправителя, служба добавила следующий адрес по умолчанию: адрес для отправки сообщения:</span><span class="sxs-lookup"><span data-stu-id="35a32-145">In the past, when Microsoft 365 or Outlook.com received a message without a From address, the service added the following default From: address to make the message deliverable:</span></span>

  `From: <>`

  <span data-ttu-id="35a32-146">Теперь сообщения с пустым адресом отстают приниматься.</span><span class="sxs-lookup"><span data-stu-id="35a32-146">Now, messages with a blank From address are no longer accepted.</span></span>

- <span data-ttu-id="35a32-147">`From: Microsoft 365 sender@contoso.com` (Отображаемое имя присутствует, но адрес электронной почты не заключен в угловые скобки.)</span><span class="sxs-lookup"><span data-stu-id="35a32-147">`From: Microsoft 365 sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="35a32-148">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Текст после адреса электронной почты.)</span><span class="sxs-lookup"><span data-stu-id="35a32-148">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Text after the email address.)</span></span>

- <span data-ttu-id="35a32-149">`From: Sender, Example <sender.example@contoso.com>` (Отображаемое имя содержит запятую, но не заключено в двойные кавычки).</span><span class="sxs-lookup"><span data-stu-id="35a32-149">`From: Sender, Example <sender.example@contoso.com>` (The display name contains a comma, but is not enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="35a32-150">`From: "Microsoft 365 <sender@contoso.com>"` (Целое значение ошибочно заключено в двойные кавычки).</span><span class="sxs-lookup"><span data-stu-id="35a32-150">`From: "Microsoft 365 <sender@contoso.com>"` (The whole value is incorrectly enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="35a32-151">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (Отображаемое имя присутствует, но адрес электронной почты не заключен в угловые скобки.)</span><span class="sxs-lookup"><span data-stu-id="35a32-151">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="35a32-152">`From: Microsoft 365<sender@contoso.com>` (Между отображаемым именем и левой угловой скобкой нет пробелов.)</span><span class="sxs-lookup"><span data-stu-id="35a32-152">`From: Microsoft 365<sender@contoso.com>` (No space between the display name and the left angle bracket.)</span></span>

- <span data-ttu-id="35a32-153">`From: "Microsoft 365"<sender@contoso.com>` (Между закрывающими двойными кавычками и левой угловой скобкой нет пробела.)</span><span class="sxs-lookup"><span data-stu-id="35a32-153">`From: "Microsoft 365"<sender@contoso.com>` (No space between the closing double quotation mark and the left angle bracket.)</span></span>

## <a name="suppress-auto-replies-to-your-custom-domain"></a><span data-ttu-id="35a32-154">Отмена автоматического ответа на пользовательский домен</span><span class="sxs-lookup"><span data-stu-id="35a32-154">Suppress auto-replies to your custom domain</span></span>

<span data-ttu-id="35a32-155">Вы не можете использовать этот параметр `From: <>` для подавления автоответов.</span><span class="sxs-lookup"><span data-stu-id="35a32-155">You can't use the value `From: <>` to suppress auto-replies.</span></span> <span data-ttu-id="35a32-156">Вместо этого необходимо настроить пустую запись MX для личного домена.</span><span class="sxs-lookup"><span data-stu-id="35a32-156">Instead, you need to set up a null MX record for your custom domain.</span></span> <span data-ttu-id="35a32-157">Автоматические ответы (и все ответы) подавляются, так как не существует опубликованного адреса, на который отвечающий сервер может отправлять сообщения.</span><span class="sxs-lookup"><span data-stu-id="35a32-157">Auto-replies (and all replies) are naturally suppressed because there is no published address that the responding server can send messages to.</span></span>

- <span data-ttu-id="35a32-158">Выберите домен электронной почты, который не может получать электронную почту.</span><span class="sxs-lookup"><span data-stu-id="35a32-158">Choose an email domain that can't receive email.</span></span> <span data-ttu-id="35a32-159">Например, если ваш основной домен — contoso.com, вы можете выбрать noreply.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="35a32-159">For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>

- <span data-ttu-id="35a32-160">Пустая запись MX для этого домена состоит из одного периода.</span><span class="sxs-lookup"><span data-stu-id="35a32-160">The null MX record for this domain consists of a single period.</span></span>

<span data-ttu-id="35a32-161">Например:</span><span class="sxs-lookup"><span data-stu-id="35a32-161">For example:</span></span>

```text
noreply.contoso.com IN MX .
```

<span data-ttu-id="35a32-162">Для получения дополнительных сведений о настройке записей MX ознакомьтесь со статьей [Создание DNS-записей на любом поставщике услуг хостинга DNS для Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="35a32-162">For more information about setting up MX records, see [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

<span data-ttu-id="35a32-163">Дополнительные сведения о публикации пустых MX приведены в статье [RFC 7505](https://tools.ietf.org/html/rfc7505).</span><span class="sxs-lookup"><span data-stu-id="35a32-163">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>

## <a name="override-from-address-enforcement"></a><span data-ttu-id="35a32-164">Переопределение из принудительного применения адресов</span><span class="sxs-lookup"><span data-stu-id="35a32-164">Override From address enforcement</span></span>

<span data-ttu-id="35a32-165">Чтобы обойти требования из адреса для входящей электронной почты, можно использовать список разрешенных IP-адресов (фильтрация подключений) или правила потока обработки почты (также называемые правилами транспорта), как описано в [статье Создание списков надежных отправителей в Microsoft 365](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="35a32-165">To bypass the From address requirements for inbound email, you can use the IP Allow List (connection filtering) or mail flow rules (also known as transport rules) as described in [Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span></span>

<span data-ttu-id="35a32-166">Вы не можете переопределить требования к адресу для исходящей электронной почты, отправляемой из Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="35a32-166">You can't override the From address requirements for outbound email that you send from Microsoft 365.</span></span> <span data-ttu-id="35a32-167">Кроме того, Outlook.com запрещает переопределение любого вида даже через поддержку.</span><span class="sxs-lookup"><span data-stu-id="35a32-167">In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span>

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a><span data-ttu-id="35a32-168">Другие способы предотвращения и защиты циберкримес в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="35a32-168">Other ways to prevent and protect against cybercrimes in Microsoft 365</span></span>

<span data-ttu-id="35a32-169">Дополнительные сведения о том, как можно усилить Организацию фишинга, нежелательной почты, нарушений данных и других угроз, можно найти [в статьях 10 наиболее распространенных способов защиты Microsoft 365 для бизнес-планов](../../admin/security-and-compliance/secure-your-business-data.md).</span><span class="sxs-lookup"><span data-stu-id="35a32-169">For more information on how you can strengthen your organization against phishing, spam, data breaches, and other threats, see [Top 10 ways to secure Microsoft 365 for business plans](../../admin/security-and-compliance/secure-your-business-data.md).</span></span>
