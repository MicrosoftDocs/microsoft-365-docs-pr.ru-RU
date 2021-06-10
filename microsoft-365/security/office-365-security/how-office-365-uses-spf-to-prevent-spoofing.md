---
title: Как структура политики отправитель (SPF) предотвращает спуфинг
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/15/2016
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3aff33c5-1416-4867-a23b-e0c0c5b4d2be
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Узнайте, Microsoft 365 использует запись TXT отправительной политики (SPF) в DNS, чтобы убедиться, что системы электронной почты назначения доверяют сообщениям, отправленным из настраиваемого домена.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 972f283f6138bafcebd877a19f0bfc429e0eed03
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205388"
---
# <a name="how-microsoft-365-uses-sender-policy-framework-spf-to-prevent-spoofing"></a><span data-ttu-id="d58fc-103">Как Microsoft 365 использует инфраструктуру политики отправителей (SPF) для предотвращения спуфинга</span><span class="sxs-lookup"><span data-stu-id="d58fc-103">How Microsoft 365 uses Sender Policy Framework (SPF) to prevent spoofing</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d58fc-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="d58fc-104">**Applies to**</span></span>
- [<span data-ttu-id="d58fc-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d58fc-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="d58fc-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="d58fc-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="d58fc-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d58fc-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

 <span data-ttu-id="d58fc-108">**Сводка:** В этой статье описывается Microsoft 365 использование записи TXT-записи TXT отправительной политики (SPF) в DNS для обеспечения доверия почтовых систем назначения к сообщениям, отправленным из настраиваемого домена.</span><span class="sxs-lookup"><span data-stu-id="d58fc-108">**Summary:** This article describes how Microsoft 365 uses the Sender Policy Framework (SPF) TXT record in DNS to ensure that destination email systems trust messages sent from your custom domain.</span></span> <span data-ttu-id="d58fc-109">Это относится к исходящие сообщения, отправленные из Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d58fc-109">This applies to outbound mail sent from Microsoft 365.</span></span> <span data-ttu-id="d58fc-110">Сообщения, отосланные Microsoft 365 получателю в Microsoft 365 всегда будут передаваться SPF.</span><span class="sxs-lookup"><span data-stu-id="d58fc-110">Messages sent from Microsoft 365 to a recipient within Microsoft 365 will always pass SPF.</span></span>

<span data-ttu-id="d58fc-p102">Запись TXT инфраструктуры политики отправителей  это запись DNS, которая помогает предотвратить спуфинг и фишинг путем проверки доменного имени, с которого отправляются сообщения. Инфраструктура политики отправителей проверяет источники сообщений, сверяя IP-адрес отправителя с предполагаемым владельцем отправляющего домена.</span><span class="sxs-lookup"><span data-stu-id="d58fc-p102">An SPF TXT record is a DNS record that helps prevent spoofing and phishing by verifying the domain name from which email messages are sent. SPF validates the origin of email messages by verifying the IP address of the sender against the alleged owner of the sending domain.</span></span>

> [!NOTE]
> <span data-ttu-id="d58fc-p103">Рабочая группа IETF признала типы записей SPF устаревшими в 2014 г. Вместо них для публикации данных инфраструктуры политики отправителей необходимо использовать записи TXT в службе DNS. Далее в этой статье для простоты используется термин "запись SPF TXT".</span><span class="sxs-lookup"><span data-stu-id="d58fc-p103">SPF record types were deprecated by the Internet Engineering Task Force (IETF) in 2014. Instead, ensure that you use TXT records in DNS to publish your SPF information. The rest of this article uses the term SPF TXT record for clarity.</span></span>

<span data-ttu-id="d58fc-116">Администраторы доменов публикуют данные инфраструктуры политики отправителей в записях типа TXT в DNS.</span><span class="sxs-lookup"><span data-stu-id="d58fc-116">Domain administrators publish SPF information in TXT records in DNS.</span></span> <span data-ttu-id="d58fc-117">Эти данные позволяют определить уполномоченные серверы исходящей почты.</span><span class="sxs-lookup"><span data-stu-id="d58fc-117">The SPF information identifies authorized outbound email servers.</span></span> <span data-ttu-id="d58fc-118">В свою очередь, конечные почтовые системы проверяют, были ли сообщения отправлены уполномоченными серверами исходящей почты.</span><span class="sxs-lookup"><span data-stu-id="d58fc-118">Destination email systems verify that messages originate from authorized outbound email servers.</span></span> <span data-ttu-id="d58fc-119">Если вы уже знакомы с SPF или у вас есть простое развертывание, и просто необходимо знать, что включить в запись SPF TXT в DNS для Microsoft 365, вы можете перейти к [Настройка SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md)в Microsoft 365, чтобы помочь предотвратить спуфинг .</span><span class="sxs-lookup"><span data-stu-id="d58fc-119">If you are already familiar with SPF, or you have a simple deployment, and just need to know what to include in your SPF TXT record in DNS for Microsoft 365, you can go to [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="d58fc-120">Если у вас нет развертывания, полностью размещенного в Microsoft 365, или вы хотите получить дополнительные сведения о том, как работает SPF или как устранить проблемы SPF для Microsoft 365, продолжайте чтение.</span><span class="sxs-lookup"><span data-stu-id="d58fc-120">If you do not have a deployment that is fully-hosted in Microsoft 365, or you want more information about how SPF works or how to troubleshoot SPF for Microsoft 365, keep reading.</span></span>

> [!NOTE]
> <span data-ttu-id="d58fc-121">Раньше, если вы также использовали SharePoint Online, в личный домен нужно было добавить другую запись SPF TXT.</span><span class="sxs-lookup"><span data-stu-id="d58fc-121">Previously, you had to add a different SPF TXT record to your custom domain if you also used SharePoint Online.</span></span> <span data-ttu-id="d58fc-122">Этого больше не требуется.</span><span class="sxs-lookup"><span data-stu-id="d58fc-122">This is no longer required.</span></span> <span data-ttu-id="d58fc-123">Это изменение необходимо для того, чтобы уведомления SharePoint Online не попадали в папку нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="d58fc-123">This change should reduce the risk of SharePoint Online notification messages ending up in the Junk Email folder.</span></span> <span data-ttu-id="d58fc-124">Вам не нужно вносить изменения сразу, но если вы получаете ошибку "слишком много просмотров", измените запись SPF TXT, как описано в настройках SPF в [Microsoft 365,](set-up-spf-in-office-365-to-help-prevent-spoofing.md)чтобы предотвратить спуфинг .</span><span class="sxs-lookup"><span data-stu-id="d58fc-124">You do not need to make any changes immediately, but if you receive the "too many lookups" error, modify your SPF TXT record as described in [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span>

## <a name="how-spf-works-to-prevent-spoofing-and-phishing-in-microsoft-365"></a><span data-ttu-id="d58fc-125">Работа SPF для предотвращения подмены и фишинга в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d58fc-125">How SPF works to prevent spoofing and phishing in Microsoft 365</span></span>
<span data-ttu-id="d58fc-126"><a name="HowSPFWorks"> </a></span><span class="sxs-lookup"><span data-stu-id="d58fc-126"><a name="HowSPFWorks"> </a></span></span>

<span data-ttu-id="d58fc-p106">Инфраструктура политики отправителей определяет, разрешено ли отправителю посылать сообщения от имени домена. Если отправителю это запрещено, то есть сообщение не проходит проверку инфраструктуры политики отправителей на сервере получателя, то политика нежелательной почты, настроенная на этом сервере, определяет, как поступить с сообщением.</span><span class="sxs-lookup"><span data-stu-id="d58fc-p106">SPF determines whether or not a sender is permitted to send on behalf of a domain. If the sender is not permitted to do so, that is, if the email fails the SPF check on the receiving server, the spam policy configured on that server determines what to do with the message.</span></span>

<span data-ttu-id="d58fc-129">Каждая запись SPF TXT содержит объявления типа записи, IP-адреса, которым разрешено отправлять сообщения из домена, и внешние домены, которым разрешено отправлять сообщения от его имени, а также правило принудительного применения.</span><span class="sxs-lookup"><span data-stu-id="d58fc-129">Each SPF TXT record contains three parts: the declaration that it is an SPF TXT record, the IP addresses that are allowed to send mail from your domain and the external domains that can send on your domain's behalf, and an enforcement rule.</span></span> <span data-ttu-id="d58fc-130">В допустимой записи SPF TXT должны присутствовать все три элемента.</span><span class="sxs-lookup"><span data-stu-id="d58fc-130">You need all three in a valid SPF TXT record.</span></span> <span data-ttu-id="d58fc-131">В этой статье описывается форма записи SPF TXT, а также описаны наилучшие методы работы с Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d58fc-131">This article describes how you form your SPF TXT record and provides best practices for working with the services in Microsoft 365.</span></span> <span data-ttu-id="d58fc-132">Кроме того, представлены ссылки на инструкции по работе с регистратором доменов для публикации записей в службе DNS.</span><span class="sxs-lookup"><span data-stu-id="d58fc-132">Links to instructions on working with your domain registrar to publish your record to DNS are also provided.</span></span>

### <a name="spf-basics-ip-addresses-allowed-to-send-from-your-custom-domain"></a><span data-ttu-id="d58fc-133">Основные сведения об инфраструктуре политики отправителей: IP-адреса, которым разрешено отправлять сообщения из личного домена</span><span class="sxs-lookup"><span data-stu-id="d58fc-133">SPF basics: IP addresses allowed to send from your custom domain</span></span>
<span data-ttu-id="d58fc-134"><a name="SPFBasicsIPaddresses"> </a></span><span class="sxs-lookup"><span data-stu-id="d58fc-134"><a name="SPFBasicsIPaddresses"> </a></span></span>

<span data-ttu-id="d58fc-135">Рассмотрим базовый синтаксис правила для инфраструктуры политики отправителей:</span><span class="sxs-lookup"><span data-stu-id="d58fc-135">Take a look at the basic syntax for an SPF rule:</span></span>

<span data-ttu-id="d58fc-136">v=spf1 \<IP\>\<enforcement rule\></span><span class="sxs-lookup"><span data-stu-id="d58fc-136">v=spf1 \<IP\> \<enforcement rule\></span></span>

<span data-ttu-id="d58fc-137">Допустим, для домена contoso.com имеется следующее правило инфраструктуры политики отправителей:</span><span class="sxs-lookup"><span data-stu-id="d58fc-137">For example, let's say the following SPF rule exists for contoso.com:</span></span>

<span data-ttu-id="d58fc-138">v=spf1 \<IP address #1\> \<IP address #2\> \<IP address #3\>\<enforcement rule\></span><span class="sxs-lookup"><span data-stu-id="d58fc-138">v=spf1 \<IP address #1\> \<IP address #2\> \<IP address #3\> \<enforcement rule\></span></span>

<span data-ttu-id="d58fc-139">В этом примере правило инфраструктуры политики отправителей разрешает почтовому серверу получать сообщения только со следующих IP-адресов для домена contoso.com:</span><span class="sxs-lookup"><span data-stu-id="d58fc-139">In this example, the SPF rule instructs the receiving email server to only accept mail from these IP addresses for the domain contoso.com:</span></span>

- <span data-ttu-id="d58fc-140">IP-адрес №1</span><span class="sxs-lookup"><span data-stu-id="d58fc-140">IP address #1</span></span>

- <span data-ttu-id="d58fc-141">IP-адрес №2</span><span class="sxs-lookup"><span data-stu-id="d58fc-141">IP address #2</span></span>

- <span data-ttu-id="d58fc-142">IP-адрес №3</span><span class="sxs-lookup"><span data-stu-id="d58fc-142">IP address #3</span></span>

<span data-ttu-id="d58fc-p108">Это правило инфраструктуры политики отправителей указывает почтовому серверу получателя, что если сообщение поступает из домена contoso.com, но не с одного из этих IP-адресов, то сервер получателя должен применять к этому сообщению правило принудительного применения. Обычно используется одно из следующих правил:</span><span class="sxs-lookup"><span data-stu-id="d58fc-p108">This SPF rule tells the receiving email server that if a message comes from contoso.com, but not from one of these three IP addresses, the receiving server should apply the enforcement rule to the message. The enforcement rule is usually one of these options:</span></span>

- <span data-ttu-id="d58fc-p109">**Серьезный сбой.** В конверт сообщения добавляется отметка "серьезный сбой", а затем соблюдается политика нежелательной почты, настроенная на сервере для этого типа сообщений.</span><span class="sxs-lookup"><span data-stu-id="d58fc-p109">**Hard fail.** Mark the message with 'hard fail' in the message envelope and then follow the receiving server's configured spam policy for this type of message.</span></span>

- <span data-ttu-id="d58fc-p110">**Мягкий сбой.** В конверт сообщения добавляется отметка "мягкий сбой". Как правило, почтовые серверы настраиваются так, чтобы все равно доставлять такие сообщения. Эта отметка не видна большинству пользователей.</span><span class="sxs-lookup"><span data-stu-id="d58fc-p110">**Soft fail.** Mark the message with 'soft fail' in the message envelope. Typically, email servers are configured to deliver these messages anyway. Most end users do not see this mark.</span></span>

- <span data-ttu-id="d58fc-p111">**Нейтральное.** Не выполняется никаких действий, то есть в конверт сообщения не добавляются отметки. Обычно это правило зарезервировано для тестирования и редко используется.</span><span class="sxs-lookup"><span data-stu-id="d58fc-p111">**Neutral.** Do nothing, that is, do not mark the message envelope. This is usually reserved for testing purposes and is rarely used.</span></span>

<span data-ttu-id="d58fc-p112">В следующих примерах показано, как инфраструктура политики отправителей работает в различных ситуациях. В этих примерах contoso.com является отправителем, а woodgrovebank.com — получателем.</span><span class="sxs-lookup"><span data-stu-id="d58fc-p112">The following examples show how SPF works in different situations. In these examples, contoso.com is the sender and woodgrovebank.com is the receiver.</span></span>

### <a name="example-1-email-authentication-of-a-message-sent-directly-from-sender-to-receiver"></a><span data-ttu-id="d58fc-156">Пример 1. Проверка подлинности сообщения электронной почты, отправленного непосредственно от отправителя к получателю</span><span class="sxs-lookup"><span data-stu-id="d58fc-156">Example 1: Email authentication of a message sent directly from sender to receiver</span></span>
<span data-ttu-id="d58fc-157"><a name="spfExample1"> </a></span><span class="sxs-lookup"><span data-stu-id="d58fc-157"><a name="spfExample1"> </a></span></span>

<span data-ttu-id="d58fc-158">Инфраструктура политики отправителей лучше всего работает с прямыми маршрутами от отправителя к получателю, например:</span><span class="sxs-lookup"><span data-stu-id="d58fc-158">SPF works best when the path from sender to receiver is direct, for example:</span></span>

![Схема, на которой показано, как инфраструктура политики отправителей проверяет подлинность электронной почты, отправляемой непосредственно с сервера на сервер.](../../media/835c20a7-ed4c-49c4-91fe-b8ebb3e452a1.jpg)

<span data-ttu-id="d58fc-160">Когда woodgrovebank.com получает сообщение, то оно проходит проверку инфраструктуры политики отправителей и проверку подлинности, если IP-адрес №1 указан в записи SPF TXT для contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d58fc-160">When woodgrovebank.com receives the message, if IP address #1 is in the SPF TXT record for contoso.com, the message passes the SPF check and is authenticated.</span></span>

### <a name="example-2-spoofed-sender-address-fails-the-spf-check"></a><span data-ttu-id="d58fc-161">Пример 2. Поддельный адрес отправителя не проходит проверку инфраструктуры политики отправителей</span><span class="sxs-lookup"><span data-stu-id="d58fc-161">Example 2: Spoofed sender address fails the SPF check</span></span>
<span data-ttu-id="d58fc-162"><a name="spfExample2"> </a></span><span class="sxs-lookup"><span data-stu-id="d58fc-162"><a name="spfExample2"> </a></span></span>

<span data-ttu-id="d58fc-163">Допустим, злоумышленнику удалось найти уязвимость в домене contoso.com:</span><span class="sxs-lookup"><span data-stu-id="d58fc-163">Suppose a phisher finds a way to spoof contoso.com:</span></span>

![Схема, на которой показано, как инфраструктура политики отправителей проверяет подлинность электронной почты, отправляемой с поддельного сервера.](../../media/235dac3d-cdc5-466e-86e0-37b5979de198.jpg)

<span data-ttu-id="d58fc-165">Так как IP-адрес №12 не указан в записи SPF TXT для домена contoso.com, сообщение не проходит проверку инфраструктуры политики отправителей, а получатель может отметить его как нежелательное.</span><span class="sxs-lookup"><span data-stu-id="d58fc-165">Since IP address #12 is not in contoso.com's SPF TXT record, the message fails the SPF check and the receiver may choose to mark it as spam.</span></span>

### <a name="example-3-spf-and-forwarded-messages"></a><span data-ttu-id="d58fc-166">Пример 3. Инфраструктура политики отправителей и пересылаемые сообщения</span><span class="sxs-lookup"><span data-stu-id="d58fc-166">Example 3: SPF and forwarded messages</span></span>
<span data-ttu-id="d58fc-167"><a name="spfExample3"> </a></span><span class="sxs-lookup"><span data-stu-id="d58fc-167"><a name="spfExample3"> </a></span></span>

<span data-ttu-id="d58fc-p113">Главный недостаток инфраструктуры политики отправителей состоит в том, что она не работает с пересылаемыми сообщениями. Допустим, пользователь домена woodgrovebank.com настроил правило пересылки, которое отправляет все сообщения в учетную запись outlook.com:</span><span class="sxs-lookup"><span data-stu-id="d58fc-p113">One drawback of SPF is that it doesn't work when an email has been forwarded. For example, suppose the user at woodgrovebank.com has set up a forwarding rule to send all email to an outlook.com account:</span></span>

![Схема, на которой показано, что инфраструктура политики отправителей не может проверить подлинность пересланного сообщения.](../../media/6e92acd6-463e-4a1b-8327-fb1cf861f356.jpg)

<span data-ttu-id="d58fc-p114">Изначально сообщение проходит проверку инфраструктуры политики отправителей в домене woodgrovebank.com, но не проходит ее в outlook.com, так как IP-адрес №25 не указан в записи SPF TXT для домена contoso.com. Затем outlook.com может отметить сообщение как нежелательное. Чтобы обойти эту проблему, используйте инфраструктуру политики отправителей вместе с другими методами проверки подлинности, например DKIM и DMARC.</span><span class="sxs-lookup"><span data-stu-id="d58fc-p114">The message originally passes the SPF check at woodgrovebank.com but it fails the SPF check at outlook.com because IP #25 is not in contoso.com's SPF TXT record. Outlook.com might then mark the message as spam. To work around this problem, use SPF in conjunction with other email authentication methods such as DKIM and DMARC.</span></span>

### <a name="spf-basics-including-third-party-domains-that-can-send-mail-on-behalf-of-your-domain"></a><span data-ttu-id="d58fc-174">Основные сведения об инфраструктуре политики отправителей: включение сторонних доменов, которые могут отправлять сообщения от имени вашего домена</span><span class="sxs-lookup"><span data-stu-id="d58fc-174">SPF basics: Including third-party domains that can send mail on behalf of your domain</span></span>
<span data-ttu-id="d58fc-175"><a name="SPFBasicsIncludes"> </a></span><span class="sxs-lookup"><span data-stu-id="d58fc-175"><a name="SPFBasicsIncludes"> </a></span></span>

<span data-ttu-id="d58fc-p115">В запись SPF TXT можно добавлять не только IP-адреса, но и домены. Для этого используются операторы include. Например, для домена contoso.com может потребоваться включить все IP-адреса почтовых серверов на доменах contoso.net и contoso.org, которые принадлежат той же организации. Для этого на домене contoso.com публикуется запись SPF TXT следующего вида:</span><span class="sxs-lookup"><span data-stu-id="d58fc-p115">In addition to IP addresses, you can also configure your SPF TXT record to include domains as senders. These are added to the SPF TXT record as "include" statements. For example, contoso.com might want to include all of the IP addresses of the mail servers from contoso.net and contoso.org which it also owns. To do this, contoso.com publishes an SPF TXT record that looks like this:</span></span>

```text
v=spf1 include:contoso.net include:contoso.org -all
```

<span data-ttu-id="d58fc-180">Когда принимающий сервер видит эту запись в DNS, он также выполняет DNS-просмотр записи SPF TXT для contoso.net, а затем для contoso.org. Если в записях для contoso.net или contoso.org будет contoso.net или contoso.org, оно будет следовать и этим.</span><span class="sxs-lookup"><span data-stu-id="d58fc-180">When the receiving server sees this record in DNS, it also performs a DNS lookup on the SPF TXT record for contoso.net and then for contoso.org. If it finds an additional include statement within the records for contoso.net or contoso.org, it will follow those too.</span></span> <span data-ttu-id="d58fc-181">Во избежание атак типа "отказ в обслуживании" для одного сообщения допускается не более 10 DNS-запросов.</span><span class="sxs-lookup"><span data-stu-id="d58fc-181">In order to help prevent denial of service attacks, the maximum number of DNS lookups for a single email message is 10.</span></span> <span data-ttu-id="d58fc-182">Каждый оператор include представляет дополнительный DNS-запрос.</span><span class="sxs-lookup"><span data-stu-id="d58fc-182">Each include statement represents an additional DNS lookup.</span></span> <span data-ttu-id="d58fc-183">Если в сообщении более 10 таких запросов, оно не проходит проверку инфраструктуры политики отправителей.</span><span class="sxs-lookup"><span data-stu-id="d58fc-183">If a message exceeds the 10 limit, the message fails SPF.</span></span> <span data-ttu-id="d58fc-184">Как только сообщение достигнет этого предела, в зависимости от способа настройки приемного сервера, отправитель может получить сообщение, в котором говорится, что сообщение создается "слишком много просмотров" или что "максимальное количество переходов для сообщения было превышено" (что может произойти, когда цикл просмотров и превзойти времявыполнения DNS).</span><span class="sxs-lookup"><span data-stu-id="d58fc-184">Once a message reaches this limit, depending on the way the receiving server is configured, the sender may get a message that says the message generated "too many lookups" or that the "maximum hop count for the message has been exceeded" (which can happen when the lookups loop and surpass the DNS timeout).</span></span> <span data-ttu-id="d58fc-185">Рекомендации по устранению неполадок см. в руб. Рекомендации по устранению неполадок для [SPF в Microsoft 365.](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot)</span><span class="sxs-lookup"><span data-stu-id="d58fc-185">For tips on how to avoid this, see [Troubleshooting: Best practices for SPF in Microsoft 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).</span></span>

## <a name="requirements-for-your-spf-txt-record-and-microsoft-365"></a><span data-ttu-id="d58fc-186">Требования к записи sPF TXT и Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d58fc-186">Requirements for your SPF TXT record and Microsoft 365</span></span>
<span data-ttu-id="d58fc-187"><a name="SPFReqsinO365"> </a></span><span class="sxs-lookup"><span data-stu-id="d58fc-187"><a name="SPFReqsinO365"> </a></span></span>

<span data-ttu-id="d58fc-188">Если вы настроили почту при Microsoft 365, вы уже создали запись SPF TXT, которая идентифицирует серверы обмена сообщениями Майкрософт в качестве законного источника почты для вашего домена.</span><span class="sxs-lookup"><span data-stu-id="d58fc-188">If you set up mail when you set up Microsoft 365, you already created an SPF TXT record that identifies the Microsoft messaging servers as a legitimate source of mail for your domain.</span></span> <span data-ttu-id="d58fc-189">Скорее всего, эта запись выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d58fc-189">This record probably looks like this:</span></span>

```text
v=spf1 include:spf.protection.outlook.com -all
```

<span data-ttu-id="d58fc-190">Если вы полностью размещены, то есть у вас нет локального почтового сервера, который отправляет исходящие сообщения, это единственная запись SPF TXT, которую необходимо опубликовать для Office 365.</span><span class="sxs-lookup"><span data-stu-id="d58fc-190">If you're a fully-hosted customer, that is, you have no on-premises mail servers that send outbound mail, this is the only SPF TXT record that you need to publish for Office 365.</span></span>

<span data-ttu-id="d58fc-191">Если у вас есть гибридное развертывание (то есть у вас есть некоторые почтовые ящики на месте и некоторые размещены в Microsoft 365), или если вы автономный клиент Exchange Online Protection (EOP) (то есть ваша организация использует EOP для защиты локального почтового ящика), следует добавить исходящий IP-адрес для каждого локального края почтовых серверов к записи SPF TXT в DNS.</span><span class="sxs-lookup"><span data-stu-id="d58fc-191">If you have a hybrid deployment (that is, you have some mailboxes on-premises and some hosted in Microsoft 365), or if you're an Exchange Online Protection (EOP) standalone customer (that is, your organization uses EOP to protect your on-premises mailboxes), you should add the outbound IP address for each of your on-premises edge mail servers to the SPF TXT record in DNS.</span></span>

## <a name="form-your-spf-txt-record-for-microsoft-365"></a><span data-ttu-id="d58fc-192">Форма записи SPF TXT для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d58fc-192">Form your SPF TXT record for Microsoft 365</span></span>
<span data-ttu-id="d58fc-193"><a name="FormYourSPF"> </a></span><span class="sxs-lookup"><span data-stu-id="d58fc-193"><a name="FormYourSPF"> </a></span></span>

<span data-ttu-id="d58fc-p118">Воспользуйтесь сведениями о синтаксисе, представленными в этой статье, чтобы создать запись SPF TXT для личного домена. Здесь описаны наиболее часто используемые варианты синтаксиса, но существуют и другие. После создания записи необходимо обновить ее у регистратора доменных имен.</span><span class="sxs-lookup"><span data-stu-id="d58fc-p118">Use the syntax information in this article to form the SPF TXT record for your custom domain. Although there are other syntax options that are not mentioned here, these are the most commonly used options. Once you have formed your record, you need to update the record at your domain registrar.</span></span>

<span data-ttu-id="d58fc-197">Сведения о доменах, которые необходимо включить для Microsoft 365, см. в дополнительных [DNS-записях,](../../enterprise/external-domain-name-system-records.md)необходимых для SPF.</span><span class="sxs-lookup"><span data-stu-id="d58fc-197">For information about the domains you will need to include for Microsoft 365, see [External DNS records required for SPF](../../enterprise/external-domain-name-system-records.md).</span></span> <span data-ttu-id="d58fc-198">Используйте [пошаговую инструкцию](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md#add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online) для обновления записей SPF (TXT) для регистратора домена.</span><span class="sxs-lookup"><span data-stu-id="d58fc-198">Use the [step-by-step instructions](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md#add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online) for updating SPF (TXT) records for your domain registrar.</span></span>

### <a name="spf-txt-record-syntax-for-microsoft-365"></a><span data-ttu-id="d58fc-199">Синтаксис записи SPF TXT для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d58fc-199">SPF TXT record syntax for Microsoft 365</span></span>
<span data-ttu-id="d58fc-200"><a name="SPFSyntaxO365"> </a></span><span class="sxs-lookup"><span data-stu-id="d58fc-200"><a name="SPFSyntaxO365"> </a></span></span>

<span data-ttu-id="d58fc-201">Типичная запись SPF TXT для Microsoft 365 имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="d58fc-201">A typical SPF TXT record for Microsoft 365 has the following syntax:</span></span>

```text
v=spf1 [<ip4>|<ip6>:<IP address>] [include:<domain name>] <enforcement rule>
```

<span data-ttu-id="d58fc-202">Например:</span><span class="sxs-lookup"><span data-stu-id="d58fc-202">For example:</span></span>

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 include:spf.protection.outlook.com -all
```

<span data-ttu-id="d58fc-203">где:</span><span class="sxs-lookup"><span data-stu-id="d58fc-203">where:</span></span>

- <span data-ttu-id="d58fc-p120">**v=spf1**  обязательный параметр. Он определяет тип записи как SPF TXT.</span><span class="sxs-lookup"><span data-stu-id="d58fc-p120">**v=spf1** is required. This defines the TXT record as an SPF TXT record.</span></span>

- <span data-ttu-id="d58fc-p121">**ip4** указывает, что используются IP-адреса версии 4. **ip6** указывает, что используются IP-адреса версии 6. При использовании IP-адресов IPv6 **ip4** в примерах следует заменить на **ip6**. Можно также указать диапазоны IP-адресов с использованием нотации CIDR, например **ip4:192.168.0.1/26**.</span><span class="sxs-lookup"><span data-stu-id="d58fc-p121">**ip4** indicates that you are using IP version 4 addresses. **ip6** indicates that you are using IP version 6 addresses. If you are using IPv6 IP addresses, replace **ip4** with **ip6** in the examples in this article. You can also specify IP address ranges using CIDR notation, for example **ip4:192.168.0.1/26**.</span></span>

- <span data-ttu-id="d58fc-210">_IP-адрес_ — это IP-адрес, который необходимо добавить к записи SPF TXT.</span><span class="sxs-lookup"><span data-stu-id="d58fc-210">_IP address_ is the IP address that you want to add to the SPF TXT record.</span></span> <span data-ttu-id="d58fc-211">Обычно это IP-адрес исходящие почтовые серверы для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d58fc-211">Usually, this is the IP address of the outbound mail server for your organization.</span></span> <span data-ttu-id="d58fc-212">Вы можете перечислить несколько исходящие почтовые серверы.</span><span class="sxs-lookup"><span data-stu-id="d58fc-212">You can list multiple outbound mail servers.</span></span> <span data-ttu-id="d58fc-213">Дополнительные сведения [см. в примере: запись SPF TXT](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365)для нескольких исходящие почтовые серверы и Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d58fc-213">For more information, see [Example: SPF TXT record for multiple outbound on-premises mail servers and Microsoft 365](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365).</span></span>

- <span data-ttu-id="d58fc-214">_domain name_ — это домен, который требуется добавить в качестве надежного отправителя.</span><span class="sxs-lookup"><span data-stu-id="d58fc-214">_domain name_ is the domain you want to add as a legitimate sender.</span></span> <span data-ttu-id="d58fc-215">Список доменных имен, которые необходимо включить для Microsoft 365, см. в статью [Внешние записи DNS, необходимые для SPF.](../../enterprise/external-domain-name-system-records.md)</span><span class="sxs-lookup"><span data-stu-id="d58fc-215">For a list of domain names you should include for Microsoft 365, see [External DNS records required for SPF](../../enterprise/external-domain-name-system-records.md).</span></span>

- <span data-ttu-id="d58fc-216">Как правило, используется одно из указанных ниже правил принудительного применения.</span><span class="sxs-lookup"><span data-stu-id="d58fc-216">Enforcement rule is usually one of the following:</span></span>

  - <span data-ttu-id="d58fc-217">-all</span><span class="sxs-lookup"><span data-stu-id="d58fc-217">-all</span></span>

    <span data-ttu-id="d58fc-p124">Указывает на серьезный сбой. Если вам известны все разрешенные IP-адреса для домена, укажите их в записи SPF TXT и используйте квалификатор -all (серьезный сбой). Кроме того, если используется только инфраструктура политики отправителей, то есть не используются DMARC и DKIM, то рекомендуется использовать квалификатор -all. Рекомендуем всегда использовать этот квалификатор.</span><span class="sxs-lookup"><span data-stu-id="d58fc-p124">Indicates hard fail. If you know all of the authorized IP addresses for your domain, list them in the SPF TXT record and use the -all (hard fail) qualifier. Also, if you are only using SPF, that is, you are not using DMARC or DKIM, you should use the -all qualifier. We recommend that you use always this qualifier.</span></span>

  - <span data-ttu-id="d58fc-222">~all</span><span class="sxs-lookup"><span data-stu-id="d58fc-222">~all</span></span>

    <span data-ttu-id="d58fc-p125">Указывает на мягкий сбой. При отсутствии полного списка IP-адресов следует использовать квалификатор ~all (мягкий сбой). Кроме того, если используется DMARC с параметром p=quarantine или p=reject, вы можете использовать квалификатор ~all. В противном случае используйте квалификатор -all.</span><span class="sxs-lookup"><span data-stu-id="d58fc-p125">Indicates soft fail. If you're not sure that you have the complete list of IP addresses, then you should use the ~all (soft fail) qualifier. Also, if you are using DMARC with p=quarantine or p=reject, then you can use ~all. Otherwise, use -all.</span></span>

  - <span data-ttu-id="d58fc-227">?all</span><span class="sxs-lookup"><span data-stu-id="d58fc-227">?all</span></span>

    <span data-ttu-id="d58fc-p126">Указывает на нейтральное состояние. Этот квалификатор используется при тестировании инфраструктуры политики отправителей. Не рекомендуем использовать его в рабочем развертывании.</span><span class="sxs-lookup"><span data-stu-id="d58fc-p126">Indicates neutral. This is used when testing SPF. We do not recommend that you use this qualifier in your live deployment.</span></span>

### <a name="example-spf-txt-record-to-use-when-all-of-your-mail-is-sent-by-microsoft-365"></a><span data-ttu-id="d58fc-231">Пример: запись SPF TXT для использования, когда вся ваша почта отправляется Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d58fc-231">Example: SPF TXT record to use when all of your mail is sent by Microsoft 365</span></span>
<span data-ttu-id="d58fc-232"><a name="ExampleSPFNoSP"> </a></span><span class="sxs-lookup"><span data-stu-id="d58fc-232"><a name="ExampleSPFNoSP"> </a></span></span>

<span data-ttu-id="d58fc-233">Если вся ваша почта отправляется Microsoft 365, используйте ее в записи SPF TXT:</span><span class="sxs-lookup"><span data-stu-id="d58fc-233">If all of your mail is sent by Microsoft 365, use this in your SPF TXT record:</span></span>

```text
v=spf1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-a-hybrid-scenario-with-one-on-premises-exchange-server-and-microsoft-365"></a><span data-ttu-id="d58fc-234">Пример: запись SPF TXT для гибридного сценария с одной локальной Exchange Server и Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d58fc-234">Example: SPF TXT record for a hybrid scenario with one on-premises Exchange Server and Microsoft 365</span></span>
<span data-ttu-id="d58fc-235"><a name="ExampleSPFHybridOneExchangeServer"> </a></span><span class="sxs-lookup"><span data-stu-id="d58fc-235"><a name="ExampleSPFHybridOneExchangeServer"> </a></span></span>

<span data-ttu-id="d58fc-236">В гибридной среде, если IP-адрес локального сервера Exchange Server  192.168.0.1, чтобы настроить правило принудительного применения для инфраструктуры политики отправителей на серьезный сбой, создайте следующую запись SPF TXT:</span><span class="sxs-lookup"><span data-stu-id="d58fc-236">In a hybrid environment, if the IP address of your on-premises Exchange Server is 192.168.0.1, in order to set the SPF enforcement rule to hard fail, form the SPF TXT record as follows:</span></span>

```text
v=spf1 ip4:192.168.0.1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-multiple-outbound-on-premises-mail-servers-and-microsoft-365"></a><span data-ttu-id="d58fc-237">Пример: запись SPF TXT для нескольких исходящие почтовые серверы и Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d58fc-237">Example: SPF TXT record for multiple outbound on-premises mail servers and Microsoft 365</span></span>
<span data-ttu-id="d58fc-238"><a name="ExampleSPFMultipleMailServerO365"> </a></span><span class="sxs-lookup"><span data-stu-id="d58fc-238"><a name="ExampleSPFMultipleMailServerO365"> </a></span></span>

<span data-ttu-id="d58fc-p127">При наличии нескольких серверов исходящей электронной почты необходимо включить IP-адрес для каждого почтового сервера в записи SPF TXT и отделить каждый IP-адрес пробелом, за которым следует выражение "ip4:". Например:</span><span class="sxs-lookup"><span data-stu-id="d58fc-p127">If you have multiple outbound mail servers, include the IP address for each mail server in the SPF TXT record and separate each IP address with a space followed by an "ip4:" statement. For example:</span></span>

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 ip4:192.168.0.3 include:spf.protection.outlook.com -all
```

## <a name="next-steps-set-up-spf-for-microsoft-365"></a><span data-ttu-id="d58fc-241">Далее: настройка SPF для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d58fc-241">Next steps: Set up SPF for Microsoft 365</span></span>
<span data-ttu-id="d58fc-242"><a name="SPFNextSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="d58fc-242"><a name="SPFNextSteps"> </a></span></span>

<span data-ttu-id="d58fc-243">После сформулирования записи SPF TXT выполните действия в настройках [SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md) в Microsoft 365, чтобы предотвратить подмену, чтобы добавить ее в домен.</span><span class="sxs-lookup"><span data-stu-id="d58fc-243">Once you have formulated your SPF TXT record, follow the steps in [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) to add it to your domain.</span></span>

<span data-ttu-id="d58fc-244">Несмотря на то что инфраструктура политики отправителей призвана предотвратить спуфинг, существуют некоторые методики, которые позволяют обойти ее.</span><span class="sxs-lookup"><span data-stu-id="d58fc-244">Although SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against.</span></span> <span data-ttu-id="d58fc-245">Чтобы защититься от них, после настройки SPF необходимо также настроить DKIM и DMARC для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d58fc-245">In order to protect against these, once you have set up SPF, you should also configure DKIM and DMARC for Microsoft 365.</span></span> <span data-ttu-id="d58fc-246">Чтобы начать работу, см. в этой ссылке Использование DKIM для проверки исходящие сообщения электронной почты, отправленной из настраиваемого [домена в Microsoft 365.](use-dkim-to-validate-outbound-email.md)</span><span class="sxs-lookup"><span data-stu-id="d58fc-246">To get started, see [Use DKIM to validate outbound email sent from your custom domain in Microsoft 365](use-dkim-to-validate-outbound-email.md).</span></span> <span data-ttu-id="d58fc-247">Затем см. статью [Использование протокола DMARC для проверки электронной почты в Microsoft 365](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="d58fc-247">Next, see [Use DMARC to validate email in Microsoft 365](use-dmarc-to-validate-email.md).</span></span>

## <a name="troubleshooting-best-practices-for-spf-in-microsoft-365"></a><span data-ttu-id="d58fc-248">Устранение неполадок: лучшие практики для SPF в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d58fc-248">Troubleshooting: Best practices for SPF in Microsoft 365</span></span>
<span data-ttu-id="d58fc-249"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="d58fc-249"><a name="SPFTroubleshoot"> </a></span></span>

<span data-ttu-id="d58fc-p129">Для личного домена можно создать только одну запись SPF TXT. Создание нескольких записей приводит к ситуации циклического перебора и сбою инфраструктуры политики отправителей. Чтобы избежать этого, вы можете создать отдельные записи для каждого поддомена. Например, создайте одну запись для домена contoso.com и еще одну для поддомена bulkmail.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d58fc-p129">You can only create one SPF TXT record for your custom domain. Creating multiple records causes a round robin situation and SPF will fail. To avoid this, you can create separate records for each subdomain. For example, create one record for contoso.com and another record for bulkmail.contoso.com.</span></span>

<span data-ttu-id="d58fc-p130">Если перед доставкой сообщения электронной почты выполняется более 10 DNS-запросов, почтовый сервер получателя сообщит о постоянной ошибке ( _permerror_), а сообщение не пройдет проверку инфраструктуры политики отправителей. Сервер получателя также может отправить отчет о недоставке, включающий ошибку примерно следующего содержания:</span><span class="sxs-lookup"><span data-stu-id="d58fc-p130">If an email message causes more than 10 DNS lookups before it is delivered, the receiving mail server will respond with a permanent error, also called a  _permerror_, and cause the message to fail the SPF check. The receiving server may also respond with a non-delivery report (NDR) that contains an error similar to these:</span></span>

- <span data-ttu-id="d58fc-256">Превышено максимальное количество прыжков для сообщения.</span><span class="sxs-lookup"><span data-stu-id="d58fc-256">The message exceeded the hop count.</span></span>

- <span data-ttu-id="d58fc-257">Для сообщения потребовалось слишком много запросов.</span><span class="sxs-lookup"><span data-stu-id="d58fc-257">The message required too many lookups.</span></span>

## <a name="avoiding-the-too-many-lookups-error-when-you-use-third-party-domains-with-microsoft-365"></a><span data-ttu-id="d58fc-258">Предотвращение ошибки "слишком много смотров" при использовании сторонних доменов с Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d58fc-258">Avoiding the "too many lookups" error when you use third-party domains with Microsoft 365</span></span>
<span data-ttu-id="d58fc-259"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="d58fc-259"><a name="SPFTroubleshoot"> </a></span></span>

<span data-ttu-id="d58fc-p131">Некоторые записи SPF TXT для сторонних доменов поручают серверу получателя выполнять большое количество DNS-запросов. Например, на момент написания этой статьи запись домена Salesforce.com содержит 5 операторов include:</span><span class="sxs-lookup"><span data-stu-id="d58fc-p131">Some SPF TXT records for third-party domains direct the receiving server to perform a large number of DNS lookups. For example, at the time of this writing, Salesforce.com contains 5 include statements in its record:</span></span>

```text
v=spf1 include:_spf.google.com
include:_spfblock.salesforce.com
include:_qa.salesforce.com
include:_spfblock1.salesforce.com
include:spf.mandrillapp.com mx ~all
```

<span data-ttu-id="d58fc-p132">Чтобы избежать ошибки, вы можете реализовать политику, согласно которой (к примеру) для отправки массовых рассылок все должны использовать специальный поддомен. Затем вы можете задать для поддомена отдельную запись SPF TXT, включающую массовые рассылки.</span><span class="sxs-lookup"><span data-stu-id="d58fc-p132">To avoid the error, you can implement a policy where anyone sending bulk email, for example, has to use a subdomain specifically for this purpose. You then define a different SPF TXT record for the subdomain that includes the bulk email.</span></span>

 <span data-ttu-id="d58fc-p133">В некоторых случаях, таких как пример с доменом salesforce.com, необходимо указывать домен в записи SPF TXT, но в остальных случаях сторонний поставщик уже создал поддомен специально для этой цели. Например, для домена exacttarget.com создан поддомен, который необходимо использовать с записью SPF TXT:</span><span class="sxs-lookup"><span data-stu-id="d58fc-p133">In some cases, like the salesforce.com example, you have to use the domain in your SPF TXT record, but in other cases, the third-party may have already created a subdomain for you to use for this purpose. For example, exacttarget.com has created a subdomain that you need to use for your SPF TXT record:</span></span>

```text
cust-spf.exacttarget.com
```

<span data-ttu-id="d58fc-266">При включении сторонних доменов в запись SPF TXT необходимо согласовать со сторонним поставщиком, какой домен или поддомен будет использоваться, чтобы соблюдать ограничение в 10 запросов.</span><span class="sxs-lookup"><span data-stu-id="d58fc-266">When you include third-party domains in your SPF TXT record, you need to confirm with the third-party which domain or subdomain to use in order to avoid running into the 10 lookup limit.</span></span>

## <a name="how-to-view-your-current-spf-txt-record-and-determine-the-number-of-lookups-that-it-requires"></a><span data-ttu-id="d58fc-267">Как просмотреть текущую запись SPF TXT и определить необходимое количество запросов</span><span class="sxs-lookup"><span data-stu-id="d58fc-267">How to view your current SPF TXT record and determine the number of lookups that it requires</span></span>
<span data-ttu-id="d58fc-268"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="d58fc-268"><a name="SPFTroubleshoot"> </a></span></span>

<span data-ttu-id="d58fc-p134">С помощью команды nslookup можно просматривать записи DNS, включая запись SPF TXT. Кроме того, при желании вы можете воспользоваться множеством бесплатных веб-средств для просмотра содержимого записи SPF TXT. Просмотрев запись SPF TXT и проследив цепь операторов include, вы можете определить, сколько DNS-запросов требуется для записи. Некоторые веб-средства даже считают и показывают эти запросы. Наблюдая за их количеством, вы сможете предотвратить постоянные ошибки (permerror) от сервера получателя при отправке сообщений из организации.</span><span class="sxs-lookup"><span data-stu-id="d58fc-p134">You can use nslookup to view your DNS records, including your SPF TXT record. Or, if you prefer, there are a number of free, online tools available that you can use to view the contents of your SPF TXT record. By looking at your SPF TXT record and following the chain of include statements and redirects, you can determine how many DNS lookups the record requires. Some online tools will even count and display these lookups for you. Keeping track of this number will help prevent messages sent from your organization from triggering a permanent error, called a permerror, from the receiving server.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="d58fc-274">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="d58fc-274">For more information</span></span>
<span data-ttu-id="d58fc-275"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="d58fc-275"><a name="SPFTroubleshoot"> </a></span></span>

<span data-ttu-id="d58fc-276">Нужна помощь, чтобы добавить запись TXT инфраструктуры политики отправителей?</span><span class="sxs-lookup"><span data-stu-id="d58fc-276">Need help adding the SPF TXT record?</span></span> <span data-ttu-id="d58fc-277">Ознакомьтесь со [статьей Создание](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md#add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online) записей DNS в любом поставщике DNS-хостинга для Microsoft 365 подробных сведений об использовании системы политики отправитель с настраиваемого домена в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d58fc-277">Read the article [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md#add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online) for detailed information about usage of Sender Policy Framework with your custom domain in Microsoft 365.</span></span> <span data-ttu-id="d58fc-278">[Заглавы сообщений](anti-spam-message-headers.md) для борьбы со спамом включают поля синтаксиса и загона, используемые Microsoft 365 проверки SPF.</span><span class="sxs-lookup"><span data-stu-id="d58fc-278">[Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Microsoft 365 for SPF checks.</span></span>
