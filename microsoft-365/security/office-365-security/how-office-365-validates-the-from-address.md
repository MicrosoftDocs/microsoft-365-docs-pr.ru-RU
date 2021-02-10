---
title: Как EOP проверяет адрес "От" для предотвращения фишинга
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
ms.openlocfilehash: e7c2cbec49082fbded857dde13f73516fd3e0fd5
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167519"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="34bb3-103">Как EOP проверяет адрес "От" для предотвращения фишинга</span><span class="sxs-lookup"><span data-stu-id="34bb3-103">How EOP validates the From address to prevent phishing</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="34bb3-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="34bb3-104">**Applies to**</span></span>
- [<span data-ttu-id="34bb3-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="34bb3-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="34bb3-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="34bb3-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="34bb3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="34bb3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="34bb3-108">Фишинговые атаки представляют собой постоянную угрозу для любой организации электронной почты.</span><span class="sxs-lookup"><span data-stu-id="34bb3-108">Phishing attacks are a constant threat to any email organization.</span></span> <span data-ttu-id="34bb3-109">Помимо поддельных [(поддельных)](anti-spoofing-protection.md)адресов электронной почты, злоумышленники часто используют в адресе отправитель значения, нарушающие интернет-стандарты.</span><span class="sxs-lookup"><span data-stu-id="34bb3-109">In addition to using [spoofed (forged) sender email addresses](anti-spoofing-protection.md), attackers often use values in the From address that violate internet standards.</span></span> <span data-ttu-id="34bb3-110">Чтобы предотвратить этот тип фишинга, Exchange Online Protection (EOP) и Outlook.com теперь требуют, чтобы входящие сообщения включали адрес "От", совместимый с RFC, как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="34bb3-110">To help prevent this type of phishing, Exchange Online Protection (EOP) and Outlook.com now require inbound messages to include an RFC-compliant From address as described in this article.</span></span> <span data-ttu-id="34bb3-111">Это право было включено в ноябре 2017 г.</span><span class="sxs-lookup"><span data-stu-id="34bb3-111">This enforcement was enabled in November 2017.</span></span>

<span data-ttu-id="34bb3-112">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="34bb3-112">**Notes**:</span></span>

- <span data-ttu-id="34bb3-113">Если вы регулярно получаете сообщения электронной почты от организаций с неправильной формы адресов "От", как описано в этой статье, рекомендуем этим организациям обновить свои почтовые серверы в соответствии с современными стандартами безопасности.</span><span class="sxs-lookup"><span data-stu-id="34bb3-113">If you regularly receive email from organizations that have malformed From addresses as described in this article, encourage these organizations to update their email servers to comply with modern security standards.</span></span>

- <span data-ttu-id="34bb3-114">Эти требования не влияют на связанное поле "Отправитель" (используется списками "Отправить от имени" и списками рассылки).</span><span class="sxs-lookup"><span data-stu-id="34bb3-114">The related Sender field (used by Send on Behalf and mailing lists) isn't affected by these requirements.</span></span> <span data-ttu-id="34bb3-115">Дополнительные сведения см. в следующей записи блога: что означает ссылка на ["отправитель" сообщения электронной почты?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)</span><span class="sxs-lookup"><span data-stu-id="34bb3-115">For more information, see the following blog post: [What do we mean when we refer to the 'sender' of an email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).</span></span>

## <a name="an-overview-of-email-message-standards"></a><span data-ttu-id="34bb3-116">Обзор стандартов сообщений электронной почты</span><span class="sxs-lookup"><span data-stu-id="34bb3-116">An overview of email message standards</span></span>

<span data-ttu-id="34bb3-117">Стандартное SMTP-сообщение электронной почты состоит из *конверта сообщения* и его содержимого.</span><span class="sxs-lookup"><span data-stu-id="34bb3-117">A standard SMTP email message consists of a *message envelope* and message content.</span></span> <span data-ttu-id="34bb3-118">Конверт сообщения содержит сведения, необходимые для передачи и доставки сообщения между SMTP-серверами.</span><span class="sxs-lookup"><span data-stu-id="34bb3-118">The message envelope contains information that's required for transmitting and delivering the message between SMTP servers.</span></span> <span data-ttu-id="34bb3-119">Содержимое сообщения разделяется на поля заголовка сообщения, которые в совокупности называются *заголовком сообщения*, и текста сообщения.</span><span class="sxs-lookup"><span data-stu-id="34bb3-119">The message content contains message header fields (collectively called the *message header*) and the message body.</span></span> <span data-ttu-id="34bb3-120">Конверт сообщения описан в [RFC 5321,](https://tools.ietf.org/html/rfc5321)а заглавная почта — в [RFC 5322.](https://tools.ietf.org/html/rfc5322)</span><span class="sxs-lookup"><span data-stu-id="34bb3-120">The message envelope is described in [RFC 5321](https://tools.ietf.org/html/rfc5321), and the message header is described in [RFC 5322](https://tools.ietf.org/html/rfc5322).</span></span> <span data-ttu-id="34bb3-121">Получатели никогда не видят фактический конверт сообщения, так как он создается в процессе передачи сообщения и фактически не является частью сообщения.</span><span class="sxs-lookup"><span data-stu-id="34bb3-121">Recipients never see the actual message envelope because it's generated by the message transmission process, and it isn't actually part of the message.</span></span>

- <span data-ttu-id="34bb3-122">Адрес (также известный как адрес `5321.MailFrom` **MAIL FROM,** отправитель P1 или отправитель конверта) это адрес электронной почты, используемый при передаче сообщения по SMTP.</span><span class="sxs-lookup"><span data-stu-id="34bb3-122">The `5321.MailFrom` address (also known as the **MAIL FROM** address, P1 sender, or envelope sender) is the email address that's used in the SMTP transmission of the message.</span></span> <span data-ttu-id="34bb3-123">Этот адрес электронной почты обычно записи в поле **"Return-Path"** в заголке сообщения (хотя отправитель может назначить другой адрес электронной почты **return-Path).**</span><span class="sxs-lookup"><span data-stu-id="34bb3-123">This email address is typically recorded in the **Return-Path** header field in the message header (although it's possible for the sender to designate a different **Return-Path** email address).</span></span>

- <span data-ttu-id="34bb3-124">(также известный как адрес отправитель или `5322.From` отправитель P2)  это адрес электронной почты в поле "От" и адрес электронной почты отправитель, который отображается в почтовых клиентах.</span><span class="sxs-lookup"><span data-stu-id="34bb3-124">The `5322.From` (also known as the From address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span></span> <span data-ttu-id="34bb3-125">В этой статье основное внимание уделяется адресу "От".</span><span class="sxs-lookup"><span data-stu-id="34bb3-125">The From address is the focus of the requirements in this article.</span></span>

<span data-ttu-id="34bb3-126">Адрес "От" подробно определяется в нескольких RFC (например, в разделах RFC 5322 3.2.3, 3.4 и 3.4.1 и [RFC 3696).](https://tools.ietf.org/html/rfc3696)</span><span class="sxs-lookup"><span data-stu-id="34bb3-126">The From address is defined in detail across several RFCs (for example, RFC 5322 sections 3.2.3, 3.4, and 3.4.1, and [RFC 3696](https://tools.ietf.org/html/rfc3696)).</span></span> <span data-ttu-id="34bb3-127">Существует множество вариантов адресов и то, что считается допустимым или недопустимым.</span><span class="sxs-lookup"><span data-stu-id="34bb3-127">There are many variations on addressing and what's considered valid or invalid.</span></span> <span data-ttu-id="34bb3-128">Чтобы упростить эту возможность, рекомендуется использовать следующий формат и определения:</span><span class="sxs-lookup"><span data-stu-id="34bb3-128">To keep it simple, we recommend the following format and definitions:</span></span>

`From: "Display Name" <EmailAddress>`

- <span data-ttu-id="34bb3-129">**Отображаемого имени**: необязательная фраза, описывая владельца адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="34bb3-129">**Display Name**: An optional phrase that describes the owner of the email address.</span></span>

  - <span data-ttu-id="34bb3-130">Рекомендуется всегда заключять отображаемое имя в двойные кавычках (),как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="34bb3-130">We recommend that you always enclose the display name in double quotation marks (") as shown.</span></span> <span data-ttu-id="34bb3-131">Если отображаемое имя содержит  запятую, строку необходимо заключить в двойные кавычка для каждого RFC 5322.</span><span class="sxs-lookup"><span data-stu-id="34bb3-131">If the display name contains a comma, you _must_ enclose the string in double quotation marks per RFC 5322.</span></span>
  - <span data-ttu-id="34bb3-132">Если адрес "От" содержит отображаемое имя, значение EmailAddress должно быть заключено в угловые скобки (< >), как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="34bb3-132">If the From address includes a display name, the EmailAddress value must be enclosed in angle brackets (< >) as shown.</span></span>
  - <span data-ttu-id="34bb3-133">Корпорация Майкрософт настоятельно рекомендует вставить пробел между отображаемой и электронной почтой.</span><span class="sxs-lookup"><span data-stu-id="34bb3-133">Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>

- <span data-ttu-id="34bb3-134">**EmailAddress**: адрес электронной почты использует `local-part@domain` формат:</span><span class="sxs-lookup"><span data-stu-id="34bb3-134">**EmailAddress**: An email address uses the format `local-part@domain`:</span></span>

  - <span data-ttu-id="34bb3-135">**локализованная часть:** строка, идентифицирует почтовый ящик, связанный с адресом.</span><span class="sxs-lookup"><span data-stu-id="34bb3-135">**local-part**: A string that identifies the mailbox associated with the address.</span></span> <span data-ttu-id="34bb3-136">Это значение уникально в пределах домена.</span><span class="sxs-lookup"><span data-stu-id="34bb3-136">This value is unique within the domain.</span></span> <span data-ttu-id="34bb3-137">Часто используется имя пользователя или GUID владельца почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="34bb3-137">Often, the mailbox owner's username or GUID is used.</span></span>
  - <span data-ttu-id="34bb3-138">**домен**: полное доменное имя (FQDN) почтового сервера, на котором размещен почтовый ящик, задаваемого локальной частью адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="34bb3-138">**domain**: The fully qualified domain name (FQDN) of the email server that hosts the mailbox identified by the local-part of the email address.</span></span>

  <span data-ttu-id="34bb3-139">Вот некоторые дополнительные вопросы, которые следует учитывать при значении EmailAddress:</span><span class="sxs-lookup"><span data-stu-id="34bb3-139">These are some additional considerations for the EmailAddress value:</span></span>

  - <span data-ttu-id="34bb3-140">Только один адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="34bb3-140">Only one email address.</span></span>
  - <span data-ttu-id="34bb3-141">Не рекомендуется разделять угловые скобки пробелами.</span><span class="sxs-lookup"><span data-stu-id="34bb3-141">We recommend that you do not separate the angle brackets with spaces.</span></span>
  - <span data-ttu-id="34bb3-142">Не включайте дополнительный текст после адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="34bb3-142">Don't include additional text after the email address.</span></span>

## <a name="examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="34bb3-143">Примеры допустимого и недопустимого адресов "От"</span><span class="sxs-lookup"><span data-stu-id="34bb3-143">Examples of valid and invalid From addresses</span></span>

<span data-ttu-id="34bb3-144">Допустимы следующие адреса электронной почты from:</span><span class="sxs-lookup"><span data-stu-id="34bb3-144">The following From email addresses are valid:</span></span>

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- <span data-ttu-id="34bb3-145">`From: < sender@contoso.com >` (Не рекомендуется, так как между угловой скобками и адресом электронной почты есть пробелы.)</span><span class="sxs-lookup"><span data-stu-id="34bb3-145">`From: < sender@contoso.com >` (Not recommended because there are spaces between the angle brackets and the email address.)</span></span>

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- <span data-ttu-id="34bb3-146">`From: Microsoft 365 <sender@contoso.com>` (Не рекомендуется, так как отображаемое имя не заключено в двойные кавычка.)</span><span class="sxs-lookup"><span data-stu-id="34bb3-146">`From: Microsoft 365 <sender@contoso.com>` (Not recommended because the display name is not enclosed in double quotation marks.)</span></span>

<span data-ttu-id="34bb3-147">Недопустимы следующие адреса электронной почты "От":</span><span class="sxs-lookup"><span data-stu-id="34bb3-147">The following From email addresses are invalid:</span></span>

- <span data-ttu-id="34bb3-148">**No From address**: Some automated messages don't include a From address.</span><span class="sxs-lookup"><span data-stu-id="34bb3-148">**No From address**: Some automated messages don't include a From address.</span></span> <span data-ttu-id="34bb3-149">В прошлом, когда Microsoft 365 или Outlook.com получали сообщение без адреса "От", служба добавила следующий адрес по умолчанию От: чтобы сообщение можно было доставить:</span><span class="sxs-lookup"><span data-stu-id="34bb3-149">In the past, when Microsoft 365 or Outlook.com received a message without a From address, the service added the following default From: address to make the message deliverable:</span></span>

  `From: <>`

  <span data-ttu-id="34bb3-150">Теперь сообщения с пустым адресом "От" больше не принимаются.</span><span class="sxs-lookup"><span data-stu-id="34bb3-150">Now, messages with a blank From address are no longer accepted.</span></span>

- <span data-ttu-id="34bb3-151">`From: Microsoft 365 sender@contoso.com` (Отображаемое имя присутствует, но адрес электронной почты не заключен в угловые скобки.)</span><span class="sxs-lookup"><span data-stu-id="34bb3-151">`From: Microsoft 365 sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="34bb3-152">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Текст после адреса электронной почты.)</span><span class="sxs-lookup"><span data-stu-id="34bb3-152">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Text after the email address.)</span></span>

- <span data-ttu-id="34bb3-153">`From: Sender, Example <sender.example@contoso.com>` (Отображаемое имя содержит запятую, но не заключено в двойные кавычка.)</span><span class="sxs-lookup"><span data-stu-id="34bb3-153">`From: Sender, Example <sender.example@contoso.com>` (The display name contains a comma, but is not enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="34bb3-154">`From: "Microsoft 365 <sender@contoso.com>"` (Все значение неправильно заключено в двойные кавычка.)</span><span class="sxs-lookup"><span data-stu-id="34bb3-154">`From: "Microsoft 365 <sender@contoso.com>"` (The whole value is incorrectly enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="34bb3-155">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (Отображаемое имя присутствует, но адрес электронной почты не заключен в угловые скобки.)</span><span class="sxs-lookup"><span data-stu-id="34bb3-155">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="34bb3-156">`From: Microsoft 365<sender@contoso.com>` (Нет пробела между отображаемой и левой угловой скобками.)</span><span class="sxs-lookup"><span data-stu-id="34bb3-156">`From: Microsoft 365<sender@contoso.com>` (No space between the display name and the left angle bracket.)</span></span>

- <span data-ttu-id="34bb3-157">`From: "Microsoft 365"<sender@contoso.com>` (Нет пробела между закрываемой двойной кавычками и левой угловой скобками.)</span><span class="sxs-lookup"><span data-stu-id="34bb3-157">`From: "Microsoft 365"<sender@contoso.com>` (No space between the closing double quotation mark and the left angle bracket.)</span></span>

## <a name="suppress-auto-replies-to-your-custom-domain"></a><span data-ttu-id="34bb3-158">Подавление автоматических ответов на пользовательский домен</span><span class="sxs-lookup"><span data-stu-id="34bb3-158">Suppress auto-replies to your custom domain</span></span>

<span data-ttu-id="34bb3-159">Значение нельзя использовать для подавления `From: <>` автоматических ответов.</span><span class="sxs-lookup"><span data-stu-id="34bb3-159">You can't use the value `From: <>` to suppress auto-replies.</span></span> <span data-ttu-id="34bb3-160">Вместо этого необходимо настроить для пользовательского домена нулевую запись MX.</span><span class="sxs-lookup"><span data-stu-id="34bb3-160">Instead, you need to set up a null MX record for your custom domain.</span></span> <span data-ttu-id="34bb3-161">Автоматические ответы (и все ответы) естественно подавляются, так как нет опубликованного адреса, на который отвечающий сервер может отправлять сообщения.</span><span class="sxs-lookup"><span data-stu-id="34bb3-161">Auto-replies (and all replies) are naturally suppressed because there is no published address that the responding server can send messages to.</span></span>

- <span data-ttu-id="34bb3-162">Выберите домен электронной почты, который не может получать электронную почту.</span><span class="sxs-lookup"><span data-stu-id="34bb3-162">Choose an email domain that can't receive email.</span></span> <span data-ttu-id="34bb3-163">Например, если основной домен contoso.com, вы можете выбрать noreply.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="34bb3-163">For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>

- <span data-ttu-id="34bb3-164">NULL-запись MX для этого домена состоит из одного периода.</span><span class="sxs-lookup"><span data-stu-id="34bb3-164">The null MX record for this domain consists of a single period.</span></span>

<span data-ttu-id="34bb3-165">Например:</span><span class="sxs-lookup"><span data-stu-id="34bb3-165">For example:</span></span>

```text
noreply.contoso.com IN MX .
```

<span data-ttu-id="34bb3-166">Дополнительные сведения о настройке записей MX см. в записях создания DNS у любого поставщика услуг размещения [DNS для Microsoft 365.](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="34bb3-166">For more information about setting up MX records, see [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

<span data-ttu-id="34bb3-167">Дополнительные сведения о публикации NULL MX см. в [RFC 7505.](https://tools.ietf.org/html/rfc7505)</span><span class="sxs-lookup"><span data-stu-id="34bb3-167">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>

## <a name="override-from-address-enforcement"></a><span data-ttu-id="34bb3-168">Переопределения от принудительных адресов</span><span class="sxs-lookup"><span data-stu-id="34bb3-168">Override From address enforcement</span></span>

<span data-ttu-id="34bb3-169">Чтобы обойти требования адресов отправитель для входящие сообщения электронной почты, можно использовать список ip-адресов (фильтрация подключений) или правила потока почты (также известные как правила транспорта), как описано в списке "Создание списков надежных отправников" в [Microsoft 365.](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="34bb3-169">To bypass the From address requirements for inbound email, you can use the IP Allow List (connection filtering) or mail flow rules (also known as transport rules) as described in [Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span></span>

<span data-ttu-id="34bb3-170">Вы не можете переопредить требования к адресу отправитель для исходящие сообщения электронной почты, отправляемые из Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="34bb3-170">You can't override the From address requirements for outbound email that you send from Microsoft 365.</span></span> <span data-ttu-id="34bb3-171">Кроме того, Outlook.com не позволит переопределять какие-либо виды, даже через поддержку.</span><span class="sxs-lookup"><span data-stu-id="34bb3-171">In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span>

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a><span data-ttu-id="34bb3-172">Другие способы предотвращения и защиты от киберпреступлений в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="34bb3-172">Other ways to prevent and protect against cybercrimes in Microsoft 365</span></span>

<span data-ttu-id="34bb3-173">Дополнительные сведения о том, как можно усилить защиту организации от фишинга, нежелательной почты, нарушений безопасности данных и других угроз, см. в 10 лучших способах защиты планов [Microsoft 365](../../admin/security-and-compliance/secure-your-business-data.md)для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="34bb3-173">For more information on how you can strengthen your organization against phishing, spam, data breaches, and other threats, see [Top 10 ways to secure Microsoft 365 for business plans](../../admin/security-and-compliance/secure-your-business-data.md).</span></span>
