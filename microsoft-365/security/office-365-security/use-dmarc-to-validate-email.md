---
title: Использование протокола DMARC для проверки электронной почты
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 4a05898c-b8e4-4eab-bd70-ee912e349737
ms.collection:
- M365-security-compliance
description: Узнайте, как настроить протокол DMARC (Domain-based Message Authentication, Reporting, and Conformance), чтобы проверять сообщения, отправленные из вашей организации.
ms.openlocfilehash: adc213ec5c47184f997a812425e53a61d7ac2da3
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016330"
---
# <a name="use-dmarc-to-validate-email"></a>Использование протокола DMARC для проверки электронной почты

Протокол [DMARC](https://dmarc.org) (Domain-based Message Authentication, Reporting, and Conformance) используется в сочетании с инфраструктурой политики отправителей (SPF) и механизмом DKIM (DomainKeys Identified Mail) для проверки подлинности отправителей и подтверждения того, что сообщения, отправленные в конечные почтовые системы из вашего домена, являются доверенными. Реализация DMARC в сочетании с SPF и DKIM обеспечивает дополнительную защиту от спуфинга и фишинга. DMARC помогает получающим почтовым системам определить, что делать с сообщениями, отправленными из вашего домена, которые не прошли проверки SPF или DKIM.

> [!TIP]
> Посетите каталог [Ассоциации информационной безопасности Майкрософт (MISA)](https://www.microsoft.com/misapartnercatalog), чтобы просмотреть сторонних поставщиков, предлагающих услуги отчетности DMARC для Microsoft 365.

## <a name="how-do-spf-and-dmarc-work-together-to-protect-email-in-microsoft-365"></a>Как SPF в сочетании с протоколом DMARC обеспечивают защиту электронной почты в Microsoft 365?

 Электронное сообщение может содержать несколько адресов отправителей. Эти адреса могут использоваться для различных целей. Вот примеры некоторых таких адресов.

- **"Mail From" address** — указывает отправителя и адрес, на который следует отправлять уведомления о возврате, если возникнут проблемы с доставкой сообщения. Этот адрес задан в конверте сообщения и обычно не отображается почтовым приложением. Он иногда называется адресом 5321.MailFrom или адресом reverse-path.

- **"From" address** — адрес, который указывается в почтовом приложении как адрес отправителя. Этот адрес указывает автора сообщения электронной почты, Этот адрес указывает автора сообщения, вернее, почтовый ящик человека или систему, где оно было создано. Это поле иногда зовется адресом 5322.From.

SPF uses a DNS TXT record to provide a list of authorized sending IP addresses for a given domain. Normally, SPF checks are only performed against the 5321.MailFrom address. This means that the 5322.From address is not authenticated when you use SPF by itself. This allows for a scenario where a user can receive a message which passes an SPF check but has a spoofed 5322.From sender address. For example, consider this SMTP transcript:

```text
S: Helo woodgrovebank.com
S: Mail from: phish@phishing.contoso.com
S: Rcpt to: astobes@tailspintoys.com
S: data
S: To: "Andrew Stobes" <astobes@tailspintoys.com>
S: From: "Woodgrove Bank Security" <security@woodgrovebank.com>
S: Subject: Woodgrove Bank - Action required
S:
S: Greetings User,
S:
S: We need to verify your banking details.
S: Please click the following link to verify that we have the right information for your account.
S:
S: https://short.url/woodgrovebank/updateaccount/12-121.aspx
S:
S: Thank you,
S: Woodgrove Bank
S: .
```

В этой записи имеются следующие адреса отправителей:

- Адрес отправителя (5321.MailFrom): phish@phishing.contoso.com

- Адрес "От" (5322.From): security@woodgrovebank.com

If you configured SPF, then the receiving server performs a check against the Mail from address phish@phishing.contoso.com. If the message came from a valid source for the domain phishing.contoso.com then the SPF check passes. Since the email client only displays the From address, the user sees that this message came from security@woodgrovebank.com. With SPF alone, the validity of woodgrovebank.com was never authenticated.

When you use DMARC, the receiving server also performs a check against the From address. In the example above, if there is a DMARC TXT record in place for woodgrovebank.com, then the check against the From address fails.

## <a name="what-is-a-dmarc-txt-record"></a>Что такое запись DMARC TXT?

Like the DNS records for SPF, the record for DMARC is a DNS text (TXT) record that helps prevent spoofing and phishing. You publish DMARC TXT records in DNS. DMARC TXT records validate the origin of email messages by verifying the IP address of an email's author against the alleged owner of the sending domain. The DMARC TXT record identifies authorized outbound email servers. Destination email systems can then verify that messages they receive originate from authorized outbound email servers.

Запись DMARC TXT корпорации Майкрософт имеет примерно следующий вид:

```text
_dmarc.microsoft.com.   3600    IN      TXT     "v=DMARC1; p=none; pct=100; rua=mailto:d@rua.agari.com; ruf=mailto:d@ruf.agari.com; fo=1"
```

Корпорация Майкрософт отправляет свои отчеты DMARC сторонней компании [Agari](https://agari.com). Эта компания собирает и анализирует полученные отчеты. Посетите [каталог MISA](https://www.microsoft.com/misapartnercatalog), чтобы просмотреть других сторонних поставщиков, предлагающих услуги отчетности DMARC для Microsoft 365.

## <a name="implement-dmarc-for-inbound-mail"></a>Реализация протокола DMARC для входящей почты

You don't have to do a thing to set up DMARC for mail that you receive in Microsoft 365. We've taken care of everything for you. If you want to learn what happens to mail that fails to pass our DMARC checks, see [How Microsoft 365 handles inbound email that fails DMARC](#how-microsoft-365-handles-inbound-email-that-fails-dmarc).

## <a name="implement-dmarc-for-outbound-mail-from-microsoft-365"></a>Реализация DMARC для исходящей почты из Microsoft 365

If you use Microsoft 365 but you aren't using a custom domain, that is, you use onmicrosoft.com, you don't need to do anything else to configure or implement DMARC for your organization. SPF is already set up for you and Microsoft 365 automatically generates a DKIM signature for your outgoing mail. For more information about this signature, see [Default behavior for DKIM and Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).

 If you have a custom domain or you are using on-premises Exchange servers in addition to Microsoft 365, you need to manually implement DMARC for your outbound mail. Implementing DMARC for your custom domain includes these steps:

- [Шаг 1. Определение допустимых источников почты для домена](#step-1-identify-valid-sources-of-mail-for-your-domain)

- [Шаг 2. Настройка SPF для вашего домена](#step-2-set-up-spf-for-your-domain)

- [Шаг 3. Настройка DKIM для вашего личного домена](#step-3-set-up-dkim-for-your-custom-domain)

- [Шаг 4. Создание записи DMARC TXT для вашего домена](#step-4-form-the-dmarc-txt-record-for-your-domain)

### <a name="step-1-identify-valid-sources-of-mail-for-your-domain"></a>Шаг 1. Определение допустимых источников почты для домена

If you have already set up SPF then you have already gone through this exercise. However, for DMARC, there are additional considerations. When identifying sources of mail for your domain there are two questions you need to answer:

- Какие IP-адреса используются для отправки почты из моего домена?

- Будут ли совпадать домены в адресах 5321.MailFrom и 5322 в сообщениях, отправляемых третьими сторонами от моего имени?

### <a name="step-2-set-up-spf-for-your-domain"></a>Шаг 2. Настройка SPF для вашего домена

Теперь, когда у вас есть список всех допустимых отправителей, можно приступать к выполнению инструкций из статьи [Настройка SPF для предотвращения спуфинга](set-up-spf-in-office-365-to-help-prevent-spoofing.md).

Например, предположим, что для отправки почты с домена contoso.com используются Exchange Online, локальный сервер Exchange с IP-адресом 192.168.0.1 и веб-приложение с IP-адресом 192.168.100.100. Тогда запись SPF TXT будет выглядеть следующим образом:

```text
contoso.com  IN  TXT  " v=spf1 ip4:192.168.0.1 ip4:192.168.100.100 include:spf.protection.outlook.com -all"
```

Рекомендуется, чтобы в записи SPF TXT учитывались сторонние отправители.

### <a name="step-3-set-up-dkim-for-your-custom-domain"></a>Шаг 3. Настройка DKIM для вашего личного домена

Once you have set up SPF, you need to set up DKIM. DKIM lets you add a digital signature to email messages in the message header. If you do not set up DKIM and instead allow Microsoft 365 to use the default DKIM configuration for your domain, DMARC may fail. This is because the default DKIM configuration uses your initial onmicrosoft.com domain as the 5322.From address, not your custom domain. This forces a mismatch between the 5321.MailFrom and the 5322.From addresses in all email sent from your domain.

If you have third-party senders that send mail on your behalf and the mail they send has mismatched 5321.MailFrom and 5322.From addresses, DMARC will fail for that email. To avoid this, you need to set up DKIM for your domain specifically with that third-party sender. This allows Microsoft 365 to authenticate email from this 3rd-party service. However, it also allows others, for example, Yahoo, Gmail, and Comcast, to verify email sent to them by the third-party as if it was email sent by you. This is beneficial because it allows your customers to build trust with your domain no matter where their mailbox is located, and at the same time Microsoft 365 won't mark a message as spam due to spoofing because it passes authentication checks for your domain.

Инструкции по настройке DKIM для вашего домена, включая порядок настройки метода DKIM для сторонних отправителей, чтобы они могли подделывать ваш домен, см. в статье [Проверка исходящей электронной почты, отправляемой с личного домена, с помощью DKIM](use-dkim-to-validate-outbound-email.md).

### <a name="step-4-form-the-dmarc-txt-record-for-your-domain"></a>Шаг 4. Создание записи DMARC TXT для вашего домена

Although there are other syntax options that are not mentioned here, these are the most commonly used options for Microsoft 365. Form the DMARC TXT record for your domain in the format:

```text
_dmarc.domain  TTL  IN  TXT  "v=DMARC1; p=policy; pct=100"
```

где:

- *domain* — домен, который нужно защитить. По умолчанию запись защищает почту из домена и всех его поддоменов. Например, если указать \_dmarc.contoso.com, то DMARC будет обеспечивать защиту почты из этого домена и всех его поддоменов, таких как housewares.contoso.com или plumbing.contoso.com.

- *TTL* should always be the equivalent of one hour. The unit used for TTL, either hours (1 hour), minutes (60 minutes), or seconds (3600 seconds), will vary depending on the registrar for your domain.

- *pct=100* — обозначает, что это правило следует применять в отношении абсолютно всей почты.

- *policy* specifies what policy you want the receiving server to follow if DMARC fails. You can set the policy to none, quarantine, or reject.

Чтобы узнать больше о параметрах, которые следует использовать, ознакомьтесь с понятиями, изложенными в разделе [Рекомендации по реализации протокола DMARC в Microsoft 365](#best-practices-for-implementing-dmarc-in-microsoft-365).

Примеры:

- Параметру "policy" присвоено значение "none"

    ```text
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=none"
    ```

- Параметру "policy" присвоено значение "quarantine"

    ```text
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=quarantine"
    ```

- Параметру "policy" присвоено значение "reject"

    ```text
    _dmarc.contoso.com  3600 IN  TXT  "v=DMARC1; p=reject"
    ```

Once you have formed your record, you need to update the record at your domain registrar. For instructions on adding the DMARC TXT record to your DNS records for Microsoft 365, see [Create DNS records for Microsoft 365 when you manage your DNS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

## <a name="best-practices-for-implementing-dmarc-in-microsoft-365"></a>Рекомендации по реализации протокола DMARC в Microsoft 365

You can implement DMARC gradually without impacting the rest of your mail flow. Create and implement a roll out plan that follows these steps. Do each of these steps first with a sub-domain, then other sub-domains, and finally with the top-level domain in your organization before moving on to the next step.

1. Организуйте отслеживание влияния реализации DMARC

    Start with a simple monitoring-mode record for a sub-domain or domain that requests that DMARC receivers send you statistics about messages that they see using that domain. A monitoring-mode record is a DMARC TXT record that has its policy set to none (p=none). Many companies publish a DMARC TXT record with p=none because they are unsure about how much email they may lose by publishing a more restrictive DMARC policy.

    You can do this even before you've implemented SPF or DKIM in your messaging infrastructure. However, you won't be able to effectively quarantine or reject mail by using DMARC until you also implement SPF and DKIM. As you introduce SPF and DKIM, the reports generated through DMARC will provide the numbers and sources of messages that pass these checks, and those that don't. You can easily see how much of your legitimate traffic is or isn't covered by them, and troubleshoot any problems. You'll also begin to see how many fraudulent messages are being sent, and from where.

2. Запросите у внешних почтовых систем помещение на карантин почты, не прошедшей проверки DMARC

    When you believe that all or most of your legitimate traffic is protected by SPF and DKIM, and you understand the impact of implementing DMARC, you can implement a quarantine policy. A quarantine policy is a DMARC TXT record that has its policy set to quarantine (p=quarantine). By doing this, you are asking DMARC receivers to put messages from your domain that fail DMARC into the local equivalent of a spam folder instead of your customers' inboxes.

3. Запросите у внешних почтовых систем не принимать сообщения, не прошедшие проверки DMARC

    The final step is implementing a reject policy. A reject policy is a DMARC TXT record that has its policy set to reject (p=reject). When you do this, you're asking DMARC receivers not to accept messages that fail the DMARC checks.

## <a name="how-microsoft-365-handles-outbound-email-that-fails-dmarc"></a>Как Microsoft 365 обрабатывает исходящую почту, не прошедшую проверку DMARC

Если исходящее из Microsoft 365 сообщение не прошло проверки DMARC, а вы реализовали политику карантина (p=quarantine) или политику отклонения (p=reject), то такое сообщение перенаправляется через [Пул доставки сообщений с более высокой степенью опасности для исходящих сообщений](high-risk-delivery-pool-for-outbound-messages.md). Возможность переопределить исходящую почту отсутствует.

If you publish a DMARC reject policy (p=reject), no other customer in Microsoft 365 can spoof your domain because messages will not be able to pass SPF or DKIM for your domain when relaying a message outbound through the service. However, if you do publish a DMARC reject policy but don't have all of your email authenticated through Microsoft 365, some of it may be marked as spam for inbound email (as described above), or it will be rejected if you do not publish SPF and try to relay it outbound through the service. This happens, for example, if you forget to include some of the IP addresses for servers and apps that send mail on behalf of your domain when you form your DMARC TXT record.

## <a name="how-microsoft-365-handles-inbound-email-that-fails-dmarc"></a>Как Microsoft 365 обрабатывает входящую почту, не прошедшую проверку DMARC

Если для отправляющего сервера задана политика отклонения DMARC `p=reject`, EOP будет отмечать сообщения как поддельные, а не отклонять их. Другими словами, в случае исходящей почты служба Microsoft 365 рассматривает политики `p=reject` и `p=quarantine` как одинаковые. Администраторы могут настроить действия для сообщений, классифицированных как поддельные, в [политике защиты от фишинга](set-up-anti-phishing-policies.md).

Такая конфигурация Microsoft 365 обусловлена тем, что некоторые допустимые сообщения могут не проходить проверки DMARC. Например, сообщение может не пройти проверки DMARC, если оно отправлено в список рассылки, который в последствии пересылает его всем получателям, указанным в списке. Если Microsoft 365 отклонит эти сообщения, получатели могут безвозвратно потерять важную почту. Вместо этого такие сообщения будут по-прежнему не проходить проверки DMARC, однако они будут отмечены как спам, а не отклонены. При необходимости пользователи могут воспользоваться приведенными ниже способами, чтобы получить такие сообщения.

- Пользователи могут добавить надежных отправителей в список с помощью своих почтовых клиентов.

- Администраторы могут обновить отчеты [аналитики спуфинга](learn-about-spoof-intelligence.md), чтобы разрешить спуфинг.

- Администраторы могут создать для всех пользователей правило обработки потока почты Exchange (правило транспорта), разрешающее отправку сообщений для этих конкретных отправителей.

Дополнительные сведения см. в статье [Создание списков надежных отправителей](create-safe-sender-lists-in-office-365.md).

## <a name="how-microsoft-365-utilizes-authenticated-received-chain-arc"></a>Как Microsoft 365 использует Authenticated Received Chain (ARC)

Все размещенные почтовые ящики в Microsoft 365 теперь получают преимущества ARC с улучшенной надежностью доставки сообщений и защитой от спуфинга. ARC сохраняет результаты проверки подлинности писем от всех посредников (переходов), когда письмо направляется с исходного сервера в почтовый ящик получателя. До ARC изменения, вносимые посредниками в маршрут письма, например правила пересылки или автоматические подписи, могли приводить к сбоям DMARC к моменту поступления письма в почтовый ящик получателя. При использовании ARC криптографическая сохранность результатов проверки подлинности позволяет Microsoft 365 подтверждать подлинность отправителя сообщения электронной почты.

В настоящее время Microsoft 365 использует ARC для подтверждения результатов проверки подлинности, если корпорация Майкрософт является подтверждающим центром ARC, но в будущем планируется добавить поддержку сторонних подтверждающих центров.

## <a name="troubleshooting-your-dmarc-implementation"></a>Устранение неполадок реализации DMARC

Если в записях MX своего домена первым указан домен, отличный от EOP, то для вашего домена не будут принудительно применяться проверки DMARC.

Если вы являетесь клиентом, а ваша основная запись MX не указывает на EOP, вы не сможете воспользоваться преимуществами DMARC. Например, DMARC не будет работать, если вы настроите запись MX таким образом, чтобы она указывала на локальный почтовый сервер, а затем перенаправите почту в EOP с помощью соединителя. В этом случае получающий домен является одним из ваших обслуживающих доменов, тогда как EOP не является основной системой обмена электронной почтой. К примеру, допустим, что в записи MX домен contoso.com указывает сам на себя и использует EOP в качестве вспомогательной записи MX, тогда запись MX для домена contoso.com будет выглядеть следующим образом:

```text
contoso.com     3600   IN  MX  0  mail.contoso.com
contoso.com     3600   IN  MX  10 contoso-com.mail.protection.outlook.com
```

Вся или почти вся электронная почта сначала будет перенаправляться в домен mail.contoso.com, поскольку это основная система обмена электронной почтой, а затем в домен EOP. В некоторых случаях вы можете даже не указать EOP в записи MX и просто воспользоваться соединителями для перенаправления почты. Домен EOP не обязательно должен быть первым элементом, для которого требуется выполнить проверку DMARC. Просто это обеспечивает проверку, так как мы не можем быть уверены, что все локальные серверы и серверы, не связанные с Office 365, выполняют проверки DMARC.  DMARC может быть принудительно применен для домена клиента (не сервера) при настройке записи TXT DMARC, но такое применение осуществляется сервером-получателем.  Если настроить EOP как сервер-получатель, EOP принудительно применит DMARC.

:::image type="content" source="../../media/Tp_DMARCTroublehoot.png" alt-text="Изображение устранения неполадок DMARC, предоставленное Дэниелом Манде":::

## <a name="for-more-information"></a>Дополнительные сведения

Want more information about DMARC? These resources can help.

- [Заголовки сообщений защиты от спама](anti-spam-message-headers.md) включают поля синтаксиса и заголовка, которые Microsoft 365 использует для проверок DMARC.

- Пройдите [курс обучения DMARC](https://www.m3aawg.org/activities/training/dmarc-training-series), предлагаемый компанией M<sup>3</sup>AAWG (Messaging, Malware, Mobile Anti-Abuse Working Group).

- Воспользуйтесь контрольным списком, представленным на сайте [dmarcian](https://space.dmarcian.com/deployment/).

- Посетите сайт источника по адресу [DMARC.org](https://dmarc.org).

## <a name="see-also"></a>См. также

[Как Microsoft 365 использует инфраструктуру политики отправителей (SPF) для предотвращения спуфинга](how-office-365-uses-spf-to-prevent-spoofing.md)

[Настройка SPF в Microsoft 365 для предотвращения спуфинга](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

[Проверка исходящей электронной почты, отправляемой с личного домена в Microsoft 365, с помощью DKIM](use-dkim-to-validate-outbound-email.md)
