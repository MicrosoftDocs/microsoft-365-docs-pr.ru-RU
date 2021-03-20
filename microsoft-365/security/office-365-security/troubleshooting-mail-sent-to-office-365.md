---
title: Письмо с устранением неполадок, отправленное в Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f4caa4e1-e414-4b21-8822-31c08064c059
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: В этой статье содержится информация об устранении неполадок при отправке электронной почты в почтовые ящики в Microsoft 365 & для массовой рассылки клиентам Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5cebb5ab3f5f4adf321e9c7992fcc5efe40ac2a2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908154"
---
# <a name="troubleshooting-mail-sent-to-microsoft-365"></a><span data-ttu-id="2e297-103">Письмо с устранением неполадок, отправленное в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2e297-103">Troubleshooting mail sent to Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2e297-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="2e297-104">**Applies to**</span></span>
- [<span data-ttu-id="2e297-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2e297-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="2e297-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="2e297-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)

<span data-ttu-id="2e297-107">В этой статье содержится информация об устранении неполадок для отправителей, у которых возникли проблемы при отправке электронной почты в почтовые ящики в Microsoft 365, а также лучшие практики массовой рассылки клиентам.</span><span class="sxs-lookup"><span data-stu-id="2e297-107">This article provides troubleshooting information for senders who are experiencing issues when trying to send email to inboxes in Microsoft 365 and best practices for bulk mailing to customers.</span></span>

## <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a><span data-ttu-id="2e297-108">Управляете ли вы репутацией своего IP-адреса и домена отправителя?</span><span class="sxs-lookup"><span data-stu-id="2e297-108">Are you managing your IP and domain's sending reputation?</span></span>

<span data-ttu-id="2e297-109">Технологии фильтрации EOP предназначены для защиты от нежелательной почты для Microsoft 365, а также для других продуктов Майкрософт, таких как Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="2e297-109">EOP filtering technologies are designed to provide anti-spam protection for Microsoft 365 as well as other Microsoft products like Exchange Server.</span></span> <span data-ttu-id="2e297-110">Мы также используем SPF, DKIM и DMARC; Технологии проверки подлинности электронной почты, которые помогают решить проблему спуфинга и фишинга, проверяя, разрешена ли отправка электронной почты доменом.</span><span class="sxs-lookup"><span data-stu-id="2e297-110">We also leverage SPF, DKIM, and DMARC; email authentication technologies that help address the problem of spoofing and phishing by verifying that the domain sending the email is authorized to do so.</span></span> <span data-ttu-id="2e297-111">Фильтрация EOP зависит от ряда факторов, связанных с отправкой IP, домена, проверки подлинности, точности списков, коэффициентов жалоб, контента и других.</span><span class="sxs-lookup"><span data-stu-id="2e297-111">EOP filtering is influenced by a number of factors related to the sending IP, domain, authentication, list accuracy, complaint rates, content and more.</span></span> <span data-ttu-id="2e297-112">Из них одним из основных факторов, влияющих на репутацию отправляющих и их возможность доставки электронной почты, является скорость жалоб на нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="2e297-112">Of these, one of the principal factors in driving down a sender's reputation and their ability to deliver email is their junk email complaint rate.</span></span>

## <a name="are-you-sending-email-from-new-ip-addresses"></a><span data-ttu-id="2e297-113">Отправляете ли вы сообщения с новых IP-адресов?</span><span class="sxs-lookup"><span data-stu-id="2e297-113">Are you sending email from new IP addresses?</span></span>

<span data-ttu-id="2e297-p102">Обычно у IP-адресов, которые ранее не использовались для отправки почты, нет репутации в наших системах. Таким образом, проблемы при доставке сообщений с новых IP-адресов возникают чаще. Если IP-адрес не рассылает спам, обычно доставка почты с него улучшается.</span><span class="sxs-lookup"><span data-stu-id="2e297-p102">IP addresses not previously used to send email typically don't have any reputation built up in our systems. As a result, emails from new IPs are more likely to experience delivery issues. Once the IP has built a reputation for not sending spam, EOP will typically allow for a better email delivery experience.</span></span>

<span data-ttu-id="2e297-p103">Новые IP-адреса, добавленные для доменов, которые прошли проверку подлинности с помощью существующих записей инфраструктуры политики отправителей, обычно наследуют часть репутации домена. Если у вашего домена хорошая репутация отправителя, то новые IP-адреса быстрее получат хорошую репутацию. Новый IP-адрес может получить хорошую репутацию в течение пары недель или быстрее в зависимости от количества отправляемой почты, точности списка и частоты поступления жалоб на спам.</span><span class="sxs-lookup"><span data-stu-id="2e297-p103">New IPs that are added for domains that are authenticated under existing SPF records typically experience the added benefit of inheriting some of the domain's sending reputation. If your domain has a good sending reputation new IPs may experience a faster ramp up time. A new IP can expect to be fully ramped within a couple of weeks or sooner depending on volume, list accuracy, and junk email complaint rates.</span></span>

## <a name="confirm-that-your-dns-is-set-up-correctly"></a><span data-ttu-id="2e297-120">Проверьте правильность настройки DNS</span><span class="sxs-lookup"><span data-stu-id="2e297-120">Confirm that your DNS is set up correctly</span></span>

<span data-ttu-id="2e297-121">Чтобы получить инструкции о том, как создавать и сохранять записи DNS, в том числе запись MX, необходимую для маршрутизации почты, обратитесь к поставщику услуг размещения DNS.</span><span class="sxs-lookup"><span data-stu-id="2e297-121">For instructions about how to create and maintain DNS records, including the MX record required for mail routing, you will need to contact your DNS hosting provider.</span></span>

## <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a><span data-ttu-id="2e297-122">Убедитесь, что вы не объявляете свой IP-адрес, как не поддерживающий маршрутизацию</span><span class="sxs-lookup"><span data-stu-id="2e297-122">Ensure that you do not advertise yourself as a non-routable IP</span></span>

<span data-ttu-id="2e297-p104">Мы можем не принять почту от отправителей после неудачного обратного запроса DNS. В некоторых случаях добропорядочные отправители неправильно сообщают, что их IP-адрес не поддерживает маршрутизацию в Интернете, при попытке подключиться к EOP. Ниже перечислены IP-адреса, зарезервированные для частных сетей (не поддерживающих маршрутизацию).</span><span class="sxs-lookup"><span data-stu-id="2e297-p104">We may not accept email from senders who fail a reverse-DNS lookup. In some cases, legitimate senders advertise themselves incorrectly as a non-internet routable IP when attempting to open a connection to EOP. IP addresses that are reserved for private (non-routable) networking include:</span></span>

- <span data-ttu-id="2e297-126">192.168.0.0/16 (или 192.168.0.0-192.168.255.255)</span><span class="sxs-lookup"><span data-stu-id="2e297-126">192.168.0.0/16 (or 192.168.0.0 - 192.168.255.255)</span></span>
- <span data-ttu-id="2e297-127">10.0.0.0/8 (или 10.0.0.0-10.255.255.255)</span><span class="sxs-lookup"><span data-stu-id="2e297-127">10.0.0.0/8 (or 10.0.0.0 - 10.255.255.255)</span></span>
- <span data-ttu-id="2e297-128">172.16.0.0/11 (или 172.16.0.0-172.31.255.255)</span><span class="sxs-lookup"><span data-stu-id="2e297-128">172.16.0.0/11 (or 172.16.0.0 - 172.31.255.255)</span></span>

## <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a><span data-ttu-id="2e297-129">Вы получили отчет о невывозе (NDR) при отправке электронной почты пользователю в Office 365</span><span class="sxs-lookup"><span data-stu-id="2e297-129">You received a non-delivery report (NDR) when sending email to a user in Office 365</span></span>

<span data-ttu-id="2e297-p105">Некоторые проблемы с доставкой возникают из-за того, что IP-адрес отправителя блокируется корпорацией Майкрософт или из-за того, что учетная запись пользователя заблокирована за рассылку спама. Если вы считаете, что получили отчет о недоставке по ошибке, то сначала выполните приведенные в нем инструкции.</span><span class="sxs-lookup"><span data-stu-id="2e297-p105">Some delivery issues are the result of the sender's IP address being blocked by Microsoft or because the user account is identified as banned sender due to previous spam activity. If you believe that you have received the NDR in error, first follow any instructions in the NDR message to resolve the issue.</span></span>

<span data-ttu-id="2e297-132">Дополнительные сведения об ошибке, которую вы получили, см. в списке кодов ошибок в отчетах о невывозе электронной почты [в Exchange Online.](/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)</span><span class="sxs-lookup"><span data-stu-id="2e297-132">For more information about the error you received, see the list of error codes in [Email non-delivery reports in Exchange Online](/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span></span>

 <span data-ttu-id="2e297-133">Например, если вы получаете следующий NDR, это указывает на то, что отправляя IP-адрес был заблокирован Корпорацией Майкрософт:</span><span class="sxs-lookup"><span data-stu-id="2e297-133">For example, if you receive the following NDR, it indicates that the sending IP address was blocked by Microsoft:</span></span>

 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`

<span data-ttu-id="2e297-134">Чтобы запросить удаление из этого списка, вы можете использовать портал делист, чтобы удалить себя из списка [заблокированных отправителей.](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)</span><span class="sxs-lookup"><span data-stu-id="2e297-134">To request removal from this list, you can [Use the delist portal to remove yourself from the blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

## <a name="my-email-landed-in-the-recipients-junk-email-folder"></a><span data-ttu-id="2e297-135">Моя электронная почта приземлилась в папке нежелательной почты получателя</span><span class="sxs-lookup"><span data-stu-id="2e297-135">My email landed in the recipient's Junk Email folder</span></span>

<span data-ttu-id="2e297-136">Если сообщение по ошибке определено как спам, попросите получателя отправить отчет о ложном срабатывании в группу анализа спама корпорации Майкрософт, которая проанализирует сообщение.</span><span class="sxs-lookup"><span data-stu-id="2e297-136">If a message was incorrectly identified as spam by EOP, you can work with the recipient to submit this false positive message to the Microsoft Spam Analysis Team, who will evaluate and analyze the message.</span></span> <span data-ttu-id="2e297-137">Для получения дополнительной информации см. [Отчет о сообщениях и файлах в Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="2e297-137">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a><span data-ttu-id="2e297-138">EOP регулирует трафик с моего IP-адреса</span><span class="sxs-lookup"><span data-stu-id="2e297-138">Traffic from my IP address is throttled by EOP</span></span>

<span data-ttu-id="2e297-139">Если вы получили отчет о недоставке от EOP, в котором указано, что EOP регулирует ваш IP-адрес, например:</span><span class="sxs-lookup"><span data-stu-id="2e297-139">If you receive an NDR from EOP that indicates that your IP address is being throttled by EOP, for example:</span></span>

 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`

<span data-ttu-id="2e297-p107">Вы получили отчет о недоставке, потому что с вашего IP-адреса выполняются подозрительные действия, и возможности IP-адреса ограничены на время проверки. Если подозрение не подтвердится, то вскоре это ограничение будет снято.</span><span class="sxs-lookup"><span data-stu-id="2e297-p107">You received the NDR because suspicious activity has been detected from the IP address and it has been temporarily restricted while it is being further evaluated. If the suspicion is cleared through evaluation, this restriction will be lifted shortly.</span></span>

## <a name="i-cant-receive-email-from-senders-in-microsoft-365"></a><span data-ttu-id="2e297-142">Я не могу получать электронную почту от отправителей в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2e297-142">I can't receive email from senders in Microsoft 365</span></span>

 <span data-ttu-id="2e297-143">Чтобы получать сообщения от наших пользователей, убедитесь, что в вашей сети разрешены подключения с IP-адресов, которые EOP использует в наших центрах обработки данных.</span><span class="sxs-lookup"><span data-stu-id="2e297-143">In order to receive messages from our users, make sure your network allows connections from the IP addresses that EOP uses in our datacenters.</span></span> <span data-ttu-id="2e297-144">Дополнительные сведения см. в [интернете IP-адреса Exchange Online Protection.](../../enterprise/urls-and-ip-address-ranges.md)</span><span class="sxs-lookup"><span data-stu-id="2e297-144">For more information, see [Exchange Online Protection IP addresses](../../enterprise/urls-and-ip-address-ranges.md).</span></span>

## <a name="best-practices-for-bulk-emailing-to-microsoft-365-users"></a><span data-ttu-id="2e297-145">Наилучшие методы массовой рассылки пользователям Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2e297-145">Best practices for bulk emailing to Microsoft 365 users</span></span>

<span data-ttu-id="2e297-146">Если вы часто проводите массовые кампании электронной почты для пользователей Microsoft 365 и хотите убедиться, что ваши сообщения поступают безопасно и своевременно, следуйте советам в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="2e297-146">If you often conduct bulk email campaigns to Microsoft 365 users and want to ensure that your emails arrive in a safe and timely manner, follow the tips in this section.</span></span>

### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a><span data-ttu-id="2e297-147">Убедитесь, что имя From отображает, кто отправляет сообщение</span><span class="sxs-lookup"><span data-stu-id="2e297-147">Ensure that the From name reflects who is sending the message</span></span>

<span data-ttu-id="2e297-p109">В теме кратко укажите, чему посвящено сообщение, а в основном тексте кратко и четко опишите предложение, услугу или продукт. Пример:</span><span class="sxs-lookup"><span data-stu-id="2e297-p109">The Subject should be a brief summary of what the message is about, and the message body should clearly and succinctly indicate what the offering, service, or product is about. For example:</span></span>

<span data-ttu-id="2e297-150">Правильный вариант:</span><span class="sxs-lookup"><span data-stu-id="2e297-150">Correct:</span></span>

> <span data-ttu-id="2e297-151">Из: marketing@shoppershandbag.com</span><span class="sxs-lookup"><span data-stu-id="2e297-151">From: marketing@shoppershandbag.com</span></span> <br> <span data-ttu-id="2e297-152">Тема: Обновленный каталог для новогоднего сезона!</span><span class="sxs-lookup"><span data-stu-id="2e297-152">Subject: Updated catalog for the Christmas season!</span></span>

<span data-ttu-id="2e297-153">Неправильный вариант:</span><span class="sxs-lookup"><span data-stu-id="2e297-153">Incorrect:</span></span>

> <span data-ttu-id="2e297-154">Из: someone@outlook.com</span><span class="sxs-lookup"><span data-stu-id="2e297-154">From: someone@outlook.com</span></span> <br> <span data-ttu-id="2e297-155">Тема: Каталоги</span><span class="sxs-lookup"><span data-stu-id="2e297-155">Subject: Catalogs</span></span>

<span data-ttu-id="2e297-156">Чем проще пользователям узнать, кто вы и чем занимаетесь, тем выше вероятность того, что сообщение будет доставлено через большинство фильтров спама.</span><span class="sxs-lookup"><span data-stu-id="2e297-156">The easier you make it for people to know who you are and what you are doing, the less difficulty you will have delivering through most spam filters.</span></span>

### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a><span data-ttu-id="2e297-157">Всегда включайте в сообщения пункт "Отменить подписку"</span><span class="sxs-lookup"><span data-stu-id="2e297-157">Always include an unsubscribe option in campaign emails</span></span>

<span data-ttu-id="2e297-p110">В рекламных сообщениях, особенно информационных бюллетенях, всегда должен быть предусмотрен способ отменить подписку. Пример:</span><span class="sxs-lookup"><span data-stu-id="2e297-p110">Marketing emails, especially newsletters, should always include a way of unsubscribing from future emails. For example:</span></span>

 `This email was sent to example@contoso.com by sender@fabrikam.com.`

 `Update Profile/Email Address | Instant removal with SafeUnsubscribe&trade; | Privacy Policy`

<span data-ttu-id="2e297-p111">Иногда чтобы отписаться, от получателей требуется отправить письмо с темой "Отменить подписку" на определенный псевдоним. Этот вариант менее предпочтителен, чем описанный выше. Если вы все-таки выберете вариант с отправкой сообщения, сделайте так, чтобы после нажатия ссылки все обязательные поля заполнялись автоматически.</span><span class="sxs-lookup"><span data-stu-id="2e297-p111">Some senders include this option by requiring recipients to send an email to a certain alias with "Unsubscribe" in the subject. This is not preferable to the one-click example above. If you do choose to require recipients to send a mail, ensure that when they click the link, all the required fields are pre-populated.</span></span>

### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a><span data-ttu-id="2e297-163">Используйте двухэтапное предоставление согласия на получение рекламных сообщений или информационных бюллетеней</span><span class="sxs-lookup"><span data-stu-id="2e297-163">Use the double opt-in option for marketing email or newsletter registration</span></span>

<span data-ttu-id="2e297-p112">Этот метод рекомендуется, если для доступа к вашим продуктам или услугам пользователям требуется регистрировать свою контактную информацию. Некоторые компании автоматически подписывают пользователей на рекламные сообщения или электронные бюллетени в процессе регистрации, но это считается сомнительной маркетинговой практикой, когда везде используется фильтрация электронной почты.</span><span class="sxs-lookup"><span data-stu-id="2e297-p112">This industry best practice is recommended if your company requires or encourages users to register their contact information in order to access your product or services. Some companies make it a practice to automatically sign up their users for marketing emails or e-newsletters during the registration process, but this is considered a questionable marketing practice in the world of email filtering.</span></span>

<span data-ttu-id="2e297-166">Если в процессе регистрации флажок "Да, отправляйте мне информационные бюллетени" или "Да, отправляйте мне специальные предложения" установлен по умолчанию, невнимательные пользователи могут случайно подписаться на невостребованные рекламные сообщения или информационные бюллетени.</span><span class="sxs-lookup"><span data-stu-id="2e297-166">During the registration process, if the "Yes, please send me your newsletter" or "Yes, please send me special offers" checkbox is selected by default, users who do not pay close attention may unintentionally sign up for marketing email or newsletters that they do not want to receive.</span></span>

 <span data-ttu-id="2e297-p113">Мы рекомендуем использовать вариант с двухэтапным предоставлением согласия, при котором указанный флажок о подписке на маркетинговые материалы или информационные бюллетени по умолчанию снят. Кроме того, после отправки регистрационной формы пользователю отправляется сообщение с URL-адресом для подтверждения подписки на рекламные сообщения.</span><span class="sxs-lookup"><span data-stu-id="2e297-p113">We recommend the double opt-in option instead, which means that the checkbox for marketing emails or newsletters is unchecked by default. Additionally, once the registration form has been submitted, a verification email is sent to the user with a URL that allows them to confirm their decision to receive marketing emails.</span></span>

 <span data-ttu-id="2e297-169">Это гарантирует, что только те пользователи, которые хотят получать рекламные сообщения, будут подписаны на них. Это снимает с рассылающей их компании все вопросы относительно используемых ею методов маркетинга.</span><span class="sxs-lookup"><span data-stu-id="2e297-169">This helps ensure that only those users who want to receive marketing email are signed up for the emails, subsequently clearing the sending company of any questionable email marketing practices.</span></span>

### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a><span data-ttu-id="2e297-170">Убедитесь, что содержимое электронного сообщения прозрачно и отслеживаемо</span><span class="sxs-lookup"><span data-stu-id="2e297-170">Ensure that email message content is transparent and traceable</span></span>

<span data-ttu-id="2e297-p114">Текст сообщений так же важен, как и способ их рассылки. Создавая текст, следуйте приведенным ниже рекомендациям, чтобы ваши сообщения не были помечены службами фильтрации почты.</span><span class="sxs-lookup"><span data-stu-id="2e297-p114">Just as important as the way the emails are sent is the content they contain. When creating email content, use the following best practices to ensure that your emails will not be flagged by email filtering services:</span></span>

- <span data-ttu-id="2e297-173">Если сообщение содержит просьбу добавить отправителя в адресную книгу, должно быть четко указано, что такое действие не является гарантией доставки.</span><span class="sxs-lookup"><span data-stu-id="2e297-173">When the email message requests that recipients add the sender to the address book, it should clearly state that such action is not a guarantee of delivery.</span></span>

- <span data-ttu-id="2e297-p115">Перенаправления, включенные в текст сообщения, должны быть похожими и унифицированными. В этом контексте перенаправление  это все, что отсылает за пределы сообщения, например ссылки и документы. Если в вашем сообщении много рекламных ссылок, ссылок для отмены подписки или обновления профиля, они должны указывать на один и тот же домен. Пример:</span><span class="sxs-lookup"><span data-stu-id="2e297-p115">Redirects included in the body of the message should be similar and consistent, and not multiple and varied. A redirect in this context is anything that points away from the message, such as links and documents. If you have a lot of advertising or Unsubscribe links or Update the Profile links, they should all point to the same domain. For example:</span></span>

  <span data-ttu-id="2e297-178">Правильно (все домены одинаковы):</span><span class="sxs-lookup"><span data-stu-id="2e297-178">Correct (all domains are the same):</span></span>

  `unsubscribe.bulkmailer.com`

  `profile.bulkmailer.com`

  `options.bulkmailer.com`

  <span data-ttu-id="2e297-179">Неправильно (все домены отличаются):</span><span class="sxs-lookup"><span data-stu-id="2e297-179">Incorrect (all domains are different):</span></span>

  `unsubscribe.bulkmailer.com`

  `profile.excite.com`

  `options.yahoo.com`

- <span data-ttu-id="2e297-180">Не следует отправлять большие изображения и вложения, а также сообщения, целиком состоящие из изображения.</span><span class="sxs-lookup"><span data-stu-id="2e297-180">Avoid content with large images and attachments, or messages that are solely composed of an image.</span></span>

- <span data-ttu-id="2e297-181">В общедоступных параметрах конфиденциальности или спецификации P3P должно быть четко указано наличие пикселей отслеживания (веб-маяков).</span><span class="sxs-lookup"><span data-stu-id="2e297-181">Your public privacy or P3P settings should clearly state the presence of tracking pixels (web bugs or beacons).</span></span>

### <a name="remove-incorrect-email-aliases-from-your-databases"></a><span data-ttu-id="2e297-182">Удалите неправильные псевдонимы электронной почты из своих баз данных</span><span class="sxs-lookup"><span data-stu-id="2e297-182">Remove incorrect email aliases from your databases</span></span>

<span data-ttu-id="2e297-p116">Любой псевдоним электронной почты в вашей базе данных, который создает сообщение возврата, не нужен и создает повод для дополнительной проверки исходящих сообщений службами фильтрации почты. Убедитесь, что база данных электронных адресов актуальна.</span><span class="sxs-lookup"><span data-stu-id="2e297-p116">Any email alias in your database that creates a bounce-back is unnecessary and puts your outbound emails at risk for further scrutiny by email filtering services. Ensure that your email database is up-to-date.</span></span>