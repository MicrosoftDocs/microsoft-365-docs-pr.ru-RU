---
title: Проверка EOP адреса From для предотвращения фишинга
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать о типах адресов электронной почты, которые принимаются или отклоняется Exchange Online Protection (EOP) и Outlook.com для предотвращения фишинга.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 71da944c02137024adda48434c5214695c54a817
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910682"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="548a7-103">Проверка EOP адреса From для предотвращения фишинга</span><span class="sxs-lookup"><span data-stu-id="548a7-103">How EOP validates the From address to prevent phishing</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="548a7-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="548a7-104">**Applies to**</span></span>
- [<span data-ttu-id="548a7-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="548a7-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="548a7-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="548a7-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="548a7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="548a7-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="548a7-108">Фишинговые атаки представляют постоянную угрозу для любой организации электронной почты.</span><span class="sxs-lookup"><span data-stu-id="548a7-108">Phishing attacks are a constant threat to any email organization.</span></span> <span data-ttu-id="548a7-109">Помимо использования поддельных [(поддельных)](anti-spoofing-protection.md)адресов электронной почты отправитель, злоумышленники часто используют значения в адресе From, которые нарушают стандарты Интернета.</span><span class="sxs-lookup"><span data-stu-id="548a7-109">In addition to using [spoofed (forged) sender email addresses](anti-spoofing-protection.md), attackers often use values in the From address that violate internet standards.</span></span> <span data-ttu-id="548a7-110">Чтобы предотвратить этот тип фишинга, Exchange Online Protection (EOP) и Outlook.com теперь требуют входящие сообщения, чтобы включить RFC-совместимый адрес From address, как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="548a7-110">To help prevent this type of phishing, Exchange Online Protection (EOP) and Outlook.com now require inbound messages to include an RFC-compliant From address as described in this article.</span></span> <span data-ttu-id="548a7-111">Это правоприменители были включены в ноябре 2017 г.</span><span class="sxs-lookup"><span data-stu-id="548a7-111">This enforcement was enabled in November 2017.</span></span>

<span data-ttu-id="548a7-112">**Примечания.**</span><span class="sxs-lookup"><span data-stu-id="548a7-112">**Notes**:</span></span>

- <span data-ttu-id="548a7-113">Если вы регулярно получаете сообщения электронной почты от организаций, у них имеются недооформленные адреса, описанные в этой статье, поощряйте эти организации обновлять свои серверы электронной почты в соответствии с современными стандартами безопасности.</span><span class="sxs-lookup"><span data-stu-id="548a7-113">If you regularly receive email from organizations that have malformed From addresses as described in this article, encourage these organizations to update their email servers to comply with modern security standards.</span></span>

- <span data-ttu-id="548a7-114">Связанное поле Отправитель (используемая send on Behalf and mailing lists) не зависит от этих требований.</span><span class="sxs-lookup"><span data-stu-id="548a7-114">The related Sender field (used by Send on Behalf and mailing lists) isn't affected by these requirements.</span></span> <span data-ttu-id="548a7-115">Дополнительные сведения см. в следующем блоге: Что мы имеем в виду, когда ссылаемся на ["отправитель" электронной почты?.](/archive/blogs/tzink/what-do-we-mean-when-we-refer-to-the-sender-of-an-email)</span><span class="sxs-lookup"><span data-stu-id="548a7-115">For more information, see the following blog post: [What do we mean when we refer to the 'sender' of an email?](/archive/blogs/tzink/what-do-we-mean-when-we-refer-to-the-sender-of-an-email).</span></span>

## <a name="an-overview-of-email-message-standards"></a><span data-ttu-id="548a7-116">Обзор стандартов сообщений электронной почты</span><span class="sxs-lookup"><span data-stu-id="548a7-116">An overview of email message standards</span></span>

<span data-ttu-id="548a7-117">Стандартное SMTP-сообщение электронной почты состоит из *конверта сообщения* и его содержимого.</span><span class="sxs-lookup"><span data-stu-id="548a7-117">A standard SMTP email message consists of a *message envelope* and message content.</span></span> <span data-ttu-id="548a7-118">Конверт сообщения содержит сведения, необходимые для передачи и доставки сообщения между серверами SMTP.</span><span class="sxs-lookup"><span data-stu-id="548a7-118">The message envelope contains information that's required for transmitting and delivering the message between SMTP servers.</span></span> <span data-ttu-id="548a7-119">Содержимое сообщения разделяется на поля заголовка сообщения, которые в совокупности называются *заголовком сообщения*, и текста сообщения.</span><span class="sxs-lookup"><span data-stu-id="548a7-119">The message content contains message header fields (collectively called the *message header*) and the message body.</span></span> <span data-ttu-id="548a7-120">Конверт сообщения описан в [RFC 5321,](https://tools.ietf.org/html/rfc5321)а заглавный заглавник сообщения описан в [RFC 5322](https://tools.ietf.org/html/rfc5322).</span><span class="sxs-lookup"><span data-stu-id="548a7-120">The message envelope is described in [RFC 5321](https://tools.ietf.org/html/rfc5321), and the message header is described in [RFC 5322](https://tools.ietf.org/html/rfc5322).</span></span> <span data-ttu-id="548a7-121">Получатели никогда не видят фактического конверта сообщения, так как он создается в процессе передачи сообщений и на самом деле не является частью сообщения.</span><span class="sxs-lookup"><span data-stu-id="548a7-121">Recipients never see the actual message envelope because it's generated by the message transmission process, and it isn't actually part of the message.</span></span>

- <span data-ttu-id="548a7-122">Адрес (также известный как `5321.MailFrom` **ПОЧТОВЫЙ АДРЕС,** отправитель P1 или отправитель конверта) — это адрес электронной почты, используемый при передаче сообщения SMTP.</span><span class="sxs-lookup"><span data-stu-id="548a7-122">The `5321.MailFrom` address (also known as the **MAIL FROM** address, P1 sender, or envelope sender) is the email address that's used in the SMTP transmission of the message.</span></span> <span data-ttu-id="548a7-123">Этот адрес электронной почты, как правило, записи в поле загонщика возвращаемого пути в загонщике сообщений (хотя отправитель может назначить другой адрес электронной почты **return-Path).** </span><span class="sxs-lookup"><span data-stu-id="548a7-123">This email address is typically recorded in the **Return-Path** header field in the message header (although it's possible for the sender to designate a different **Return-Path** email address).</span></span>

- <span data-ttu-id="548a7-124">(также известный как отправитель From address или P2) — это адрес электронной почты в поле From header, а также адрес электронной почты отправитель, отображаемый в клиентах электронной `5322.From` почты. </span><span class="sxs-lookup"><span data-stu-id="548a7-124">The `5322.From` (also known as the From address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span></span> <span data-ttu-id="548a7-125">Адрес From находится в центре внимания требований в этой статье.</span><span class="sxs-lookup"><span data-stu-id="548a7-125">The From address is the focus of the requirements in this article.</span></span>

<span data-ttu-id="548a7-126">Адрес From подробно определяется в нескольких RFCs (например, разделы RFC 5322 3.2.3, 3.4 и 3.4.1 и [RFC 3696).](https://tools.ietf.org/html/rfc3696)</span><span class="sxs-lookup"><span data-stu-id="548a7-126">The From address is defined in detail across several RFCs (for example, RFC 5322 sections 3.2.3, 3.4, and 3.4.1, and [RFC 3696](https://tools.ietf.org/html/rfc3696)).</span></span> <span data-ttu-id="548a7-127">Существует множество вариантов решения и того, что считается допустимым или недействительным.</span><span class="sxs-lookup"><span data-stu-id="548a7-127">There are many variations on addressing and what's considered valid or invalid.</span></span> <span data-ttu-id="548a7-128">Чтобы упростить процесс, рекомендуется использовать следующий формат и определения:</span><span class="sxs-lookup"><span data-stu-id="548a7-128">To keep it simple, we recommend the following format and definitions:</span></span>

`From: "Display Name" <EmailAddress>`

- <span data-ttu-id="548a7-129">**Имя отображения:** необязательная фраза, описываемая владельцем адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="548a7-129">**Display Name**: An optional phrase that describes the owner of the email address.</span></span>

  - <span data-ttu-id="548a7-130">Мы рекомендуем всегда заключить имя дисплея в двойные кавычка (), как показано.</span><span class="sxs-lookup"><span data-stu-id="548a7-130">We recommend that you always enclose the display name in double quotation marks (") as shown.</span></span> <span data-ttu-id="548a7-131">Если имя дисплея содержит  запятую, строку необходимо оградить двойными кавычками на RFC 5322.</span><span class="sxs-lookup"><span data-stu-id="548a7-131">If the display name contains a comma, you _must_ enclose the string in double quotation marks per RFC 5322.</span></span>
  - <span data-ttu-id="548a7-132">Если адрес From содержит отображаемое имя, значение EmailAddress должно быть заключено в угловые скобки (< >), как показано.</span><span class="sxs-lookup"><span data-stu-id="548a7-132">If the From address includes a display name, the EmailAddress value must be enclosed in angle brackets (< >) as shown.</span></span>
  - <span data-ttu-id="548a7-133">Корпорация Майкрософт настоятельно рекомендует вставить пробел между именем дисплея и адресом электронной почты.</span><span class="sxs-lookup"><span data-stu-id="548a7-133">Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>

- <span data-ttu-id="548a7-134">**EmailAddress:** адрес электронной почты использует `local-part@domain` формат:</span><span class="sxs-lookup"><span data-stu-id="548a7-134">**EmailAddress**: An email address uses the format `local-part@domain`:</span></span>

  - <span data-ttu-id="548a7-135">**локализованная часть:** строка, определяемая почтовым ящиком, связанным с адресом.</span><span class="sxs-lookup"><span data-stu-id="548a7-135">**local-part**: A string that identifies the mailbox associated with the address.</span></span> <span data-ttu-id="548a7-136">Это уникальное значение в домене.</span><span class="sxs-lookup"><span data-stu-id="548a7-136">This value is unique within the domain.</span></span> <span data-ttu-id="548a7-137">Часто используется имя пользователя или GUID владельца почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="548a7-137">Often, the mailbox owner's username or GUID is used.</span></span>
  - <span data-ttu-id="548a7-138">**домен.** Полное доменное имя (FQDN) сервера электронной почты, на котором размещен почтовый ящик, идентифицированный локальной частью адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="548a7-138">**domain**: The fully qualified domain name (FQDN) of the email server that hosts the mailbox identified by the local-part of the email address.</span></span>

  <span data-ttu-id="548a7-139">Вот некоторые дополнительные соображения для значения EmailAddress:</span><span class="sxs-lookup"><span data-stu-id="548a7-139">These are some additional considerations for the EmailAddress value:</span></span>

  - <span data-ttu-id="548a7-140">Только один адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="548a7-140">Only one email address.</span></span>
  - <span data-ttu-id="548a7-141">Рекомендуется не отделять угловые скобки пробелами.</span><span class="sxs-lookup"><span data-stu-id="548a7-141">We recommend that you do not separate the angle brackets with spaces.</span></span>
  - <span data-ttu-id="548a7-142">Не включайте дополнительный текст после адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="548a7-142">Don't include additional text after the email address.</span></span>

## <a name="examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="548a7-143">Примеры допустимого и недействительным По адресам</span><span class="sxs-lookup"><span data-stu-id="548a7-143">Examples of valid and invalid From addresses</span></span>

<span data-ttu-id="548a7-144">Допустимы следующие адреса электронной почты:</span><span class="sxs-lookup"><span data-stu-id="548a7-144">The following From email addresses are valid:</span></span>

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- <span data-ttu-id="548a7-145">`From: < sender@contoso.com >` (Не рекомендуется, так как между скобками углов и адресом электронной почты есть пробелы.)</span><span class="sxs-lookup"><span data-stu-id="548a7-145">`From: < sender@contoso.com >` (Not recommended because there are spaces between the angle brackets and the email address.)</span></span>

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- <span data-ttu-id="548a7-146">`From: Microsoft 365 <sender@contoso.com>` (Не рекомендуется, так как имя отображения не заключено в двойные кавычка.)</span><span class="sxs-lookup"><span data-stu-id="548a7-146">`From: Microsoft 365 <sender@contoso.com>` (Not recommended because the display name is not enclosed in double quotation marks.)</span></span>

<span data-ttu-id="548a7-147">Недействительны следующие адреса электронной почты:</span><span class="sxs-lookup"><span data-stu-id="548a7-147">The following From email addresses are invalid:</span></span>

- <span data-ttu-id="548a7-148">**Нет адреса.** Некоторые автоматические сообщения не включают адрес From.</span><span class="sxs-lookup"><span data-stu-id="548a7-148">**No From address**: Some automated messages don't include a From address.</span></span> <span data-ttu-id="548a7-149">В прошлом, когда Microsoft 365 или Outlook.com получали сообщение без адреса From, служба добавила следующий по умолчанию Адрес: адрес, чтобы сделать сообщение доставляемым:</span><span class="sxs-lookup"><span data-stu-id="548a7-149">In the past, when Microsoft 365 or Outlook.com received a message without a From address, the service added the following default From: address to make the message deliverable:</span></span>

  `From: <>`

  <span data-ttu-id="548a7-150">Теперь сообщения с пустым адресом From больше не принимаются.</span><span class="sxs-lookup"><span data-stu-id="548a7-150">Now, messages with a blank From address are no longer accepted.</span></span>

- <span data-ttu-id="548a7-151">`From: Microsoft 365 sender@contoso.com` (Отображаемое имя присутствует, но адрес электронной почты не заключен в угловые скобки.)</span><span class="sxs-lookup"><span data-stu-id="548a7-151">`From: Microsoft 365 sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="548a7-152">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Текст после адреса электронной почты.)</span><span class="sxs-lookup"><span data-stu-id="548a7-152">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Text after the email address.)</span></span>

- <span data-ttu-id="548a7-153">`From: Sender, Example <sender.example@contoso.com>` (Имя отображения содержит запятую, но не заключено в двойные кавычка.)</span><span class="sxs-lookup"><span data-stu-id="548a7-153">`From: Sender, Example <sender.example@contoso.com>` (The display name contains a comma, but is not enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="548a7-154">`From: "Microsoft 365 <sender@contoso.com>"` (Все значение неправильно заключено в двойные кавычка.)</span><span class="sxs-lookup"><span data-stu-id="548a7-154">`From: "Microsoft 365 <sender@contoso.com>"` (The whole value is incorrectly enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="548a7-155">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (Отображаемое имя присутствует, но адрес электронной почты не заключен в угловые скобки.)</span><span class="sxs-lookup"><span data-stu-id="548a7-155">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="548a7-156">`From: Microsoft 365<sender@contoso.com>` (Нет места между именем дисплея и кронштейном левого угла.)</span><span class="sxs-lookup"><span data-stu-id="548a7-156">`From: Microsoft 365<sender@contoso.com>` (No space between the display name and the left angle bracket.)</span></span>

- <span data-ttu-id="548a7-157">`From: "Microsoft 365"<sender@contoso.com>` (Нет места между закрываемой двойной кавычками и кронштейном левого угла.)</span><span class="sxs-lookup"><span data-stu-id="548a7-157">`From: "Microsoft 365"<sender@contoso.com>` (No space between the closing double quotation mark and the left angle bracket.)</span></span>

## <a name="suppress-auto-replies-to-your-custom-domain"></a><span data-ttu-id="548a7-158">Подавление автоматических ответов на настраиваемый домен</span><span class="sxs-lookup"><span data-stu-id="548a7-158">Suppress auto-replies to your custom domain</span></span>

<span data-ttu-id="548a7-159">Значение нельзя использовать для подавления `From: <>` автоматических ответов.</span><span class="sxs-lookup"><span data-stu-id="548a7-159">You can't use the value `From: <>` to suppress auto-replies.</span></span> <span data-ttu-id="548a7-160">Вместо этого необходимо настроить запись null MX для пользовательского домена.</span><span class="sxs-lookup"><span data-stu-id="548a7-160">Instead, you need to set up a null MX record for your custom domain.</span></span> <span data-ttu-id="548a7-161">Автоматические ответы (и все ответы) естественно подавляются, так как нет опубликованного адреса, на который сервер ответа может отправлять сообщения.</span><span class="sxs-lookup"><span data-stu-id="548a7-161">Auto-replies (and all replies) are naturally suppressed because there is no published address that the responding server can send messages to.</span></span>

- <span data-ttu-id="548a7-162">Выберите домен электронной почты, который не может получать электронную почту.</span><span class="sxs-lookup"><span data-stu-id="548a7-162">Choose an email domain that can't receive email.</span></span> <span data-ttu-id="548a7-163">Например, если основной домен contoso.com, вы можете выбрать noreply.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="548a7-163">For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>

- <span data-ttu-id="548a7-164">Запись null MX для этого домена состоит из одного периода.</span><span class="sxs-lookup"><span data-stu-id="548a7-164">The null MX record for this domain consists of a single period.</span></span>

<span data-ttu-id="548a7-165">Например:</span><span class="sxs-lookup"><span data-stu-id="548a7-165">For example:</span></span>

```text
noreply.contoso.com IN MX .
```

<span data-ttu-id="548a7-166">Дополнительные сведения о настройке записей MX см. в ссылке [Create DNS records at any DNS hosting provider for Microsoft 365.](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="548a7-166">For more information about setting up MX records, see [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

<span data-ttu-id="548a7-167">Дополнительные сведения о публикации null MX см. в [публикации RFC 7505.](https://tools.ietf.org/html/rfc7505)</span><span class="sxs-lookup"><span data-stu-id="548a7-167">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>

## <a name="override-from-address-enforcement"></a><span data-ttu-id="548a7-168">Переопределять правоприменители адресов</span><span class="sxs-lookup"><span data-stu-id="548a7-168">Override From address enforcement</span></span>

<span data-ttu-id="548a7-169">Чтобы обойти требования к адресам для входящие сообщения электронной почты, можно использовать список IP-адресов (фильтрация подключений) или правила потока почты (также известные как правила транспорта), как описано в "Создание списков безопасного отправитель в [Microsoft 365".](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="548a7-169">To bypass the From address requirements for inbound email, you can use the IP Allow List (connection filtering) or mail flow rules (also known as transport rules) as described in [Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span></span>

<span data-ttu-id="548a7-170">Вы не можете переопредить требования "От адреса" для исходящие сообщения электронной почты, отправленные из Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="548a7-170">You can't override the From address requirements for outbound email that you send from Microsoft 365.</span></span> <span data-ttu-id="548a7-171">Кроме того, Outlook.com не разрешает переопределения любого рода, даже с помощью поддержки.</span><span class="sxs-lookup"><span data-stu-id="548a7-171">In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span>

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a><span data-ttu-id="548a7-172">Другие способы предотвращения и защиты от киберпреступлений в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="548a7-172">Other ways to prevent and protect against cybercrimes in Microsoft 365</span></span>

<span data-ttu-id="548a7-173">Дополнительные сведения о том, как укрепить организацию от фишинга, нежелательной почты, нарушений данных и других угроз, см. в [топ-10](../../admin/security-and-compliance/secure-your-business-data.md)способов защиты Microsoft 365 для бизнес-планов.</span><span class="sxs-lookup"><span data-stu-id="548a7-173">For more information on how you can strengthen your organization against phishing, spam, data breaches, and other threats, see [Top 10 ways to secure Microsoft 365 for business plans](../../admin/security-and-compliance/secure-your-business-data.md).</span></span>