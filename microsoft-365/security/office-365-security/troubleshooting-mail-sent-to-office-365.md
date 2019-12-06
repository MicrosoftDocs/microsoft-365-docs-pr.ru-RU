---
title: Устранение неполадок с отправкой почты в Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f4caa4e1-e414-4b21-8822-31c08064c059
ms.collection:
- M365-security-compliance
description: В этой статье приведены сведения об устранении неполадок при отправке почты в почтовые ящики в Office 365 и рекомендации по массовой рассылке почты клиентам Office 365.
ms.openlocfilehash: 44fe5b984c22a4560da6cf8d63096775f5b47095
ms.sourcegitcommit: 2468bcb01625f97a322459814d81b9faad717859
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "39872015"
---
# <a name="troubleshooting-mail-sent-to-office-365"></a><span data-ttu-id="6e3a4-103">Устранение неполадок с отправкой почты в Office 365</span><span class="sxs-lookup"><span data-stu-id="6e3a4-103">Troubleshooting mail sent to Office 365</span></span>

<span data-ttu-id="6e3a4-104">В этой статье приведены сведения об устранении неполадок при отправке почты в почтовые ящики в Office 365 и рекомендации по массовой рассылке почты клиентам Office 365.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-104">This article provides troubleshooting information for senders who are experiencing issues when trying to send email to inboxes in Office 365 and best practices for bulk mailing to Office 365 customers.</span></span>

## <a name="troubleshooting-common-problems-with-mail-delivery-to-office-365"></a><span data-ttu-id="6e3a4-105">Устранение распространенных проблем с доставкой почты в Office 365</span><span class="sxs-lookup"><span data-stu-id="6e3a4-105">Troubleshooting common problems with mail delivery to Office 365</span></span>

<span data-ttu-id="6e3a4-106">Выберите одну из указанных ниже распространенных проблем.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-106">Choose from one of these commonly encountered issues.</span></span>

- [<span data-ttu-id="6e3a4-107">Управляете ли вы репутацией своего IP-адреса и домена отправителя?</span><span class="sxs-lookup"><span data-stu-id="6e3a4-107">Are you managing your IP and domain's sending reputation?</span></span>](#are-you-managing-your-ip-and-domains-sending-reputation)

- [<span data-ttu-id="6e3a4-108">Отправляете ли вы сообщения с новых IP-адресов?</span><span class="sxs-lookup"><span data-stu-id="6e3a4-108">Are you sending email from new IP addresses?</span></span>](#are-you-sending-email-from-new-ip-addresses)

- [<span data-ttu-id="6e3a4-109">Проверьте правильность настройки DNS</span><span class="sxs-lookup"><span data-stu-id="6e3a4-109">Confirm that your DNS is set up correctly</span></span>](#confirm-that-your-dns-is-set-up-correctly)

- [<span data-ttu-id="6e3a4-110">Убедитесь, что вы не объявляете свой IP-адрес, как не поддерживающий маршрутизацию</span><span class="sxs-lookup"><span data-stu-id="6e3a4-110">Ensure that you do not advertise yourself as a non-routable IP</span></span>](#ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip)

- [<span data-ttu-id="6e3a4-111">Вы получили отчет о недоставке при отправке сообщения пользователю в Office 365</span><span class="sxs-lookup"><span data-stu-id="6e3a4-111">You received a non-delivery report (NDR) when sending email to a user in Office 365</span></span>](#you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365)

- [<span data-ttu-id="6e3a4-112">Мое письмо попало в папку "Спам" получателя в EOP</span><span class="sxs-lookup"><span data-stu-id="6e3a4-112">My email landed in the recipient's junk folder in EOP</span></span>](#my-email-landed-in-the-recipients-junk-folder-in-eop)

- [<span data-ttu-id="6e3a4-113">EOP регулирует трафик с моего IP-адреса</span><span class="sxs-lookup"><span data-stu-id="6e3a4-113">Traffic from my IP address is throttled by EOP</span></span>](#traffic-from-my-ip-address-is-throttled-by-eop)

### <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a><span data-ttu-id="6e3a4-114">Управляете ли вы репутацией своего IP-адреса и домена отправителя?</span><span class="sxs-lookup"><span data-stu-id="6e3a4-114">Are you managing your IP and domain's sending reputation?</span></span>

<span data-ttu-id="6e3a4-p101">Технологии фильтрации EOP предназначены для защиты Microsoft Office 365 и других продуктов Майкрософт, например Exchange Server, Microsoft Office Outlook и Windows Live Mail, от спама. Мы также используем инфраструктуру политики отправителей, DKIM и DMARC. Эти технологии помогают решить проблему спуфинга и фишинга, проверяя, разрешено ли домену отправлять почту. Фильтрация EOP зависит от ряда факторов, связанных с IP-адресом и доменом отправителя, проверкой подлинности, точностью списка, частотой поступления жалоб, содержимым и прочим. Один из основных факторов снижения репутации отправителя — это частота поступления жалоб на спам. </span><span class="sxs-lookup"><span data-stu-id="6e3a4-p101">EOP filtering technologies are designed to provide anti-spam protections for Microsoft Office 365 as well as other Microsoft products like Exchange Server, Microsoft Office Outlook, and Windows Live Mail. We also leverage SPF, DKIM, and DMARC; email authentication technologies that help address the problem of spoofing and phishing by verifying that the domain sending the email is authorized to do so. EOP filtering is influenced by a number of factors related to the sending IP, domain, authentication, list accuracy, complaint rates, content and more. Of these, one of the principal factors in driving down a sender's reputation and their ability to deliver email is their junk email complaint rate.</span></span>

### <a name="are-you-sending-email-from-new-ip-addresses"></a><span data-ttu-id="6e3a4-119">Отправляете ли вы сообщения с новых IP-адресов?</span><span class="sxs-lookup"><span data-stu-id="6e3a4-119">Are you sending email from new IP addresses?</span></span>

<span data-ttu-id="6e3a4-p102">Обычно у IP-адресов, которые ранее не использовались для отправки почты, нет репутации в наших системах. Таким образом, проблемы при доставке сообщений с новых IP-адресов возникают чаще. Если IP-адрес не рассылает спам, обычно доставка почты с него улучшается.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-p102">IP addresses not previously used to send email typically don't have any reputation built up in our systems. As a result, emails from new IPs are more likely to experience delivery issues. Once the IP has built a reputation for not sending spam, EOP will typically allow for a better email delivery experience.</span></span>

<span data-ttu-id="6e3a4-p103">Новые IP-адреса, добавленные для доменов, которые прошли проверку подлинности с помощью существующих записей инфраструктуры политики отправителей, обычно наследуют часть репутации домена. Если у вашего домена хорошая репутация отправителя, то новые IP-адреса быстрее получат хорошую репутацию. Новый IP-адрес может получить хорошую репутацию в течение пары недель или быстрее в зависимости от количества отправляемой почты, точности списка и частоты поступления жалоб на спам.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-p103">New IPs that are added for domains that are authenticated under existing SPF records typically experience the added benefit of inheriting some of the domain's sending reputation. If your domain has a good sending reputation new IPs may experience a faster ramp up time. A new IP can expect to be fully ramped within a couple of weeks or sooner depending on volume, list accuracy, and junk email complaint rates.</span></span>

### <a name="confirm-that-your-dns-is-set-up-correctly"></a><span data-ttu-id="6e3a4-126">Проверьте правильность настройки DNS</span><span class="sxs-lookup"><span data-stu-id="6e3a4-126">Confirm that your DNS is set up correctly</span></span>

<span data-ttu-id="6e3a4-127">Чтобы получить инструкции о том, как создавать и сохранять записи DNS, в том числе запись MX, необходимую для маршрутизации почты, обратитесь к поставщику услуг размещения DNS.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-127">For instructions about how to create and maintain DNS records, including the MX record required for mail routing, you will need to contact your DNS hosting provider.</span></span>

### <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a><span data-ttu-id="6e3a4-128">Убедитесь, что вы не объявляете свой IP-адрес, как не поддерживающий маршрутизацию</span><span class="sxs-lookup"><span data-stu-id="6e3a4-128">Ensure that you do not advertise yourself as a non-routable IP</span></span>

<span data-ttu-id="6e3a4-p104">Мы можем не принять почту от отправителей после неудачного обратного запроса DNS. В некоторых случаях добропорядочные отправители неправильно сообщают, что их IP-адрес не поддерживает маршрутизацию в Интернете, при попытке подключиться к EOP. Ниже перечислены IP-адреса, зарезервированные для частных сетей (не поддерживающих маршрутизацию).</span><span class="sxs-lookup"><span data-stu-id="6e3a4-p104">We may not accept email from senders who fail a reverse-DNS lookup. In some cases, legitimate senders advertise themselves incorrectly as a non-internet routable IP when attempting to open a connection to EOP. IP addresses that are reserved for private (non-routable) networking include:</span></span>

- <span data-ttu-id="6e3a4-132">192.168.0.0/16 (или 192.168.0.0-192.168.255.255)</span><span class="sxs-lookup"><span data-stu-id="6e3a4-132">192.168.0.0/16 (or 192.168.0.0 - 192.168.255.255)</span></span>

- <span data-ttu-id="6e3a4-133">10.0.0.0/8 (или 10.0.0.0-10.255.255.255)</span><span class="sxs-lookup"><span data-stu-id="6e3a4-133">10.0.0.0/8 (or 10.0.0.0 - 10.255.255.255)</span></span>

- <span data-ttu-id="6e3a4-134">172.16.0.0/11 (или 172.16.0.0-172.31.255.255)</span><span class="sxs-lookup"><span data-stu-id="6e3a4-134">172.16.0.0/11 (or 172.16.0.0 - 172.31.255.255)</span></span>

### <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a><span data-ttu-id="6e3a4-135">Вы получили отчет о недоставке при отправке сообщения электронной почты пользователю в Office 365</span><span class="sxs-lookup"><span data-stu-id="6e3a4-135">You received a non-delivery report (NDR) when sending email to a user in Office 365</span></span>

<span data-ttu-id="6e3a4-p105">Некоторые проблемы с доставкой возникают из-за того, что IP-адрес отправителя блокируется корпорацией Майкрософт или из-за того, что учетная запись пользователя заблокирована за рассылку спама. Если вы считаете, что получили отчет о недоставке по ошибке, то сначала выполните приведенные в нем инструкции.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-p105">Some delivery issues are the result of the sender's IP address being blocked by Microsoft or because the user account is identified as banned sender due to previous spam activity. If you believe that you have received the NDR in error, first follow any instructions in the NDR message to resolve the issue.</span></span>

<span data-ttu-id="6e3a4-138">Для получения дополнительных сведений о полученной ошибке обратитесь к списку кодов ошибок в [отчетах о недоставке электронной почты в Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="6e3a4-138">For more information about the error you received, see the list of error codes in [Email non-delivery reports in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span></span>

 <span data-ttu-id="6e3a4-139">Например, если вы получаете указанный ниже отчет о недоставке, ваш IP-адрес отправителя заблокирован корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-139">For example, if you receive the following NDR, it indicates that the sending IP address was blocked by Microsoft.</span></span>

 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`

<span data-ttu-id="6e3a4-140">Сведения о том, как отправить запрос на удаление IP-адреса из этого списка, см. в статье [Удаление себя из списка заблокированных отправителей Office 365 с помощью портала удаления из списка](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span><span class="sxs-lookup"><span data-stu-id="6e3a4-140">To request removal from this list, you can [Use the delist portal to remove yourself from the Office 365 blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

### <a name="my-email-landed-in-the-recipients-junk-folder-in-eop"></a><span data-ttu-id="6e3a4-141">Мое письмо попало в папку "Спам" получателя в EOP</span><span class="sxs-lookup"><span data-stu-id="6e3a4-141">My email landed in the recipient's junk folder in EOP</span></span>

<span data-ttu-id="6e3a4-p106">Если сообщение по ошибке определено как спам, попросите получателя отправить отчет о ложном срабатывании в группу анализа спама корпорации Майкрософт, которая проанализирует сообщение. В зависимости от результатов анализа мы можем изменить правила фильтрации содержимого для защиты системы от спама, чтобы доставить сообщение. Вы можете отправить по электронной почте в корпорацию Майкрософт сообщения, которые не должны классифицироваться как спам. Для этого обязательно выполните действия, описанные ниже.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-p106">If a message was incorrectly identified as spam by EOP, you can work with the recipient to submit this false positive message to the Microsoft Spam Analysis Team, who will evaluate and analyze the message. Depending on the results of the analysis, the service-wide spam content filter rules may be adjusted to allow the message through. You use email to submit messages to Microsoft that should not be classified as spam. When doing so, be sure to use the steps in the following procedure.</span></span>

### <a name="to-use-email-to-submit-false-positive-messages-to-the-microsoft-spam-analysis-team"></a><span data-ttu-id="6e3a4-146">Отправка сообщений о ложном срабатывании в группу анализа спама корпорации Майкрософт по электронной почте</span><span class="sxs-lookup"><span data-stu-id="6e3a4-146">To use email to submit false positive messages to the Microsoft Spam Analysis Team</span></span>

1. <span data-ttu-id="6e3a4-147">Сохраните сообщение, не являющееся спамом, которое вы хотите отправить в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-147">Save the message you want to submit as non-spam.</span></span>

2. <span data-ttu-id="6e3a4-148">Создайте пустое сообщение и вложите в него это сообщение.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-148">Create a new, blank message and attach the non-spam message to it.</span></span>

    <span data-ttu-id="6e3a4-149">Если необходимо, вы можете вложить несколько сообщений, не являющихся спамом.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-149">You can attach multiple non-spam messages if needed.</span></span>

3. <span data-ttu-id="6e3a4-150">Скопируйте и вставьте строку темы исходного сообщения в строку темы нового сообщения.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-150">Copy and paste the original message subject line into the new message subject line.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="6e3a4-151">Оставьте текст нового сообщения пустым.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-151">Leave the body of the new message empty.</span></span>

4. <span data-ttu-id="6e3a4-152">Отправьте это сообщение по адресу [not_junk@office365.microsoft.com](mailto:not_junk@office365.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="6e3a4-152">Send your new message to [not_junk@office365.microsoft.com](mailto:not_junk@office365.microsoft.com).</span></span>

### <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a><span data-ttu-id="6e3a4-153">EOP регулирует трафик с моего IP-адреса</span><span class="sxs-lookup"><span data-stu-id="6e3a4-153">Traffic from my IP address is throttled by EOP</span></span>

<span data-ttu-id="6e3a4-154">Если вы получили отчет о недоставке от EOP, в котором указано, что EOP регулирует ваш IP-адрес, например:</span><span class="sxs-lookup"><span data-stu-id="6e3a4-154">If you receive an NDR from EOP that indicates that your IP address is being throttled by EOP, for example:</span></span>

 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`

<span data-ttu-id="6e3a4-p107">Вы получили отчет о недоставке, потому что с вашего IP-адреса выполняются подозрительные действия, и возможности IP-адреса ограничены на время проверки. Если подозрение не подтвердится, то вскоре это ограничение будет снято.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-p107">You received the NDR because suspicious activity has been detected from the IP address and it has been temporarily restricted while it is being further evaluated. If the suspicion is cleared through evaluation, this restriction will be lifted shortly.</span></span>

### <a name="i-cant-receive-email-from-senders-in-office-365"></a><span data-ttu-id="6e3a4-157">Я не получаю почту от пользователей Office 365</span><span class="sxs-lookup"><span data-stu-id="6e3a4-157">I can't receive email from senders in Office 365</span></span>

 <span data-ttu-id="6e3a4-158">Чтобы получать сообщения от наших пользователей, убедитесь, что в вашей сети разрешены подключения с IP-адресов, которые EOP использует в наших центрах обработки данных.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-158">In order to receive messages from our users, make sure your network allows connections from the IP addresses that EOP uses in our datacenters.</span></span> <span data-ttu-id="6e3a4-159">Для получения дополнительных сведений обратитесь к разделу [IP-адреса Exchange Online Protection](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="6e3a4-159">For more information, see [Exchange Online Protection IP addresses](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

## <a name="best-practices-for-bulk-emailing-to-office-365-users"></a><span data-ttu-id="6e3a4-160">Рекомендации по массовой рассылке почты пользователям Office 365</span><span class="sxs-lookup"><span data-stu-id="6e3a4-160">Best practices for bulk emailing to Office 365 users</span></span>

<span data-ttu-id="6e3a4-161">Если вы часто проводите кампании по массовой рассылке почты пользователям Office 365 и хотите, чтобы ваши сообщения своевременно доставлялись, воспользуйтесь советами в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-161">If you often conduct bulk email campaigns to Office 365 users and want to ensure that your emails arrive in a safe and timely manner, follow the tips in this section.</span></span>

### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a><span data-ttu-id="6e3a4-162">Убедитесь, что имя в поле "От" соответствует отправителю</span><span class="sxs-lookup"><span data-stu-id="6e3a4-162">Ensure that the From: name reflects who is sending the message</span></span>

<span data-ttu-id="6e3a4-p109">В теме кратко укажите, чему посвящено сообщение, а в основном тексте кратко и четко опишите предложение, услугу или продукт. Пример:</span><span class="sxs-lookup"><span data-stu-id="6e3a4-p109">The Subject should be a brief summary of what the message is about, and the message body should clearly and succinctly indicate what the offering, service, or product is about. For example:</span></span>

<span data-ttu-id="6e3a4-165">Правильный вариант:</span><span class="sxs-lookup"><span data-stu-id="6e3a4-165">Correct:</span></span>

> <span data-ttu-id="6e3a4-166">От: marketing@shoppershandbag.com</span><span class="sxs-lookup"><span data-stu-id="6e3a4-166">From: marketing@shoppershandbag.com</span></span> <br/> <span data-ttu-id="6e3a4-167">Тема: обновлен каталог для Рождество!</span><span class="sxs-lookup"><span data-stu-id="6e3a4-167">Subject: Updated catalog for the Christmas season!</span></span>

<span data-ttu-id="6e3a4-168">Неправильный вариант:</span><span class="sxs-lookup"><span data-stu-id="6e3a4-168">Incorrect:</span></span>

> <span data-ttu-id="6e3a4-169">От: someone@outlook.com</span><span class="sxs-lookup"><span data-stu-id="6e3a4-169">From: someone@outlook.com</span></span> <br/> <span data-ttu-id="6e3a4-170">Тема: Каталоги</span><span class="sxs-lookup"><span data-stu-id="6e3a4-170">Subject: Catalogs</span></span>

<span data-ttu-id="6e3a4-171">Чем проще пользователям узнать, кто вы и чем занимаетесь, тем выше вероятность того, что сообщение будет доставлено через большинство фильтров спама.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-171">The easier you make it for people to know who you are and what you are doing, the less difficulty you will have delivering through most spam filters.</span></span>

### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a><span data-ttu-id="6e3a4-172">Всегда включайте в сообщения пункт "Отменить подписку"</span><span class="sxs-lookup"><span data-stu-id="6e3a4-172">Always include an unsubscribe option in campaign emails</span></span>

<span data-ttu-id="6e3a4-p110">В рекламных сообщениях, особенно информационных бюллетенях, всегда должен быть предусмотрен способ отменить подписку. Пример:</span><span class="sxs-lookup"><span data-stu-id="6e3a4-p110">Marketing emails, especially newsletters, should always include a way of unsubscribing from future emails. For example:</span></span>

 `This email was sent to example@contoso.com by sender@fabrikam.com.`

 `Update Profile/Email Address | Instant removal with SafeUnsubscribe™ | Privacy Policy`

<span data-ttu-id="6e3a4-p111">Иногда чтобы отписаться, от получателей требуется отправить письмо с темой "Отменить подписку" на определенный псевдоним. Этот вариант менее предпочтителен, чем описанный выше. Если вы все-таки выберете вариант с отправкой сообщения, сделайте так, чтобы после нажатия ссылки все обязательные поля заполнялись автоматически.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-p111">Some senders include this option by requiring recipients to send an email to a certain alias with "Unsubscribe" in the subject. This is not preferable to the one-click example above. If you do choose to require recipients to send a mail, ensure that when they click the link, all the required fields are pre-populated.</span></span>

### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a><span data-ttu-id="6e3a4-178">Используйте двухэтапное предоставление согласия на получение рекламных сообщений или информационных бюллетеней</span><span class="sxs-lookup"><span data-stu-id="6e3a4-178">Use the double opt-in option for marketing email or newsletter registration</span></span>

<span data-ttu-id="6e3a4-p112">Этот метод рекомендуется, если для доступа к вашим продуктам или услугам пользователям требуется регистрировать свою контактную информацию. Некоторые компании автоматически подписывают пользователей на рекламные сообщения или электронные бюллетени в процессе регистрации, но это считается сомнительной маркетинговой практикой, когда везде используется фильтрация электронной почты.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-p112">This industry best practice is recommended if your company requires or encourages users to register their contact information in order to access your product or services. Some companies make it a practice to automatically sign up their users for marketing emails or e-newsletters during the registration process, but this is considered a questionable marketing practice in the world of email filtering.</span></span>

<span data-ttu-id="6e3a4-181">Если в процессе регистрации флажок "Да, отправляйте мне информационные бюллетени" или "Да, отправляйте мне специальные предложения" установлен по умолчанию, невнимательные пользователи могут случайно подписаться на невостребованные рекламные сообщения или информационные бюллетени.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-181">During the registration process, if the "Yes, please send me your newsletter" or "Yes, please send me special offers" checkbox is selected by default, users who do not pay close attention may unintentionally sign up for marketing email or newsletters that they do not want to receive.</span></span>

 <span data-ttu-id="6e3a4-p113">Мы рекомендуем использовать вариант с двухэтапным предоставлением согласия, при котором указанный флажок о подписке на маркетинговые материалы или информационные бюллетени по умолчанию снят. Кроме того, после отправки регистрационной формы пользователю отправляется сообщение с URL-адресом для подтверждения подписки на рекламные сообщения.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-p113">We recommend the double opt-in option instead, which means that the checkbox for marketing emails or newsletters is unchecked by default. Additionally, once the registration form has been submitted, a verification email is sent to the user with a URL that allows them to confirm their decision to receive marketing emails.</span></span>

 <span data-ttu-id="6e3a4-184">Это гарантирует, что только те пользователи, которые хотят получать рекламные сообщения, будут подписаны на них. Это снимает с рассылающей их компании все вопросы относительно используемых ею методов маркетинга.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-184">This helps ensure that only those users who want to receive marketing email are signed up for the emails, subsequently clearing the sending company of any questionable email marketing practices.</span></span>

### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a><span data-ttu-id="6e3a4-185">Убедитесь, что содержимое электронного сообщения прозрачно и отслеживаемо</span><span class="sxs-lookup"><span data-stu-id="6e3a4-185">Ensure that email message content is transparent and traceable</span></span>

<span data-ttu-id="6e3a4-p114">Текст сообщений так же важен, как и способ их рассылки. Создавая текст, следуйте приведенным ниже рекомендациям, чтобы ваши сообщения не были помечены службами фильтрации почты.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-p114">Just as important as the way the emails are sent is the content they contain. When creating email content, use the following best practices to ensure that your emails will not be flagged by email filtering services:</span></span>

- <span data-ttu-id="6e3a4-188">Если сообщение содержит просьбу добавить отправителя в адресную книгу, должно быть четко указано, что такое действие не является гарантией доставки.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-188">When the email message requests that recipients add the sender to the address book, it should clearly state that such action is not a guarantee of delivery.</span></span>

- <span data-ttu-id="6e3a4-p115">Перенаправления, включенные в текст сообщения, должны быть похожими и унифицированными. В этом контексте перенаправление  это все, что отсылает за пределы сообщения, например ссылки и документы. Если в вашем сообщении много рекламных ссылок, ссылок для отмены подписки или обновления профиля, они должны указывать на один и тот же домен. Пример:</span><span class="sxs-lookup"><span data-stu-id="6e3a4-p115">Redirects included in the body of the message should be similar and consistent, and not multiple and varied. A redirect in this context is anything that points away from the message, such as links and documents. If you have a lot of advertising or Unsubscribe links or Update the Profile links, they should all point to the same domain. For example:</span></span>

  <span data-ttu-id="6e3a4-193">Правильный вариант:</span><span class="sxs-lookup"><span data-stu-id="6e3a4-193">Correct:</span></span>

  `unsubscribe.bulkmailer.com`

  `profile.bulkmailer.com`

  `options.bulkmailer.com`

  <span data-ttu-id="6e3a4-194">Неправильный вариант:</span><span class="sxs-lookup"><span data-stu-id="6e3a4-194">Incorrect:</span></span>

  `unsubscribe.bulkmailer.com`

  `profiles.excite.com`

  `options.yahoo.com`

- <span data-ttu-id="6e3a4-195">Не следует отправлять большие изображения и вложения, а также сообщения, целиком состоящие из изображения.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-195">Avoid content with large images and attachments, or messages that are solely composed of an image.</span></span>

- <span data-ttu-id="6e3a4-196">В общедоступных параметрах конфиденциальности или спецификации P3P должно быть четко указано наличие пикселей отслеживания (веб-маяков).</span><span class="sxs-lookup"><span data-stu-id="6e3a4-196">Your public privacy or P3P settings should clearly state the presence of tracking pixels (web bugs or beacons).</span></span>

### <a name="remove-incorrect-email-aliases-from-your-databases"></a><span data-ttu-id="6e3a4-197">Удалите неправильные псевдонимы электронной почты из своих баз данных</span><span class="sxs-lookup"><span data-stu-id="6e3a4-197">Remove incorrect email aliases from your databases</span></span>

<span data-ttu-id="6e3a4-p116">Любой псевдоним электронной почты в вашей базе данных, который создает сообщение возврата, не нужен и создает повод для дополнительной проверки исходящих сообщений службами фильтрации почты. Убедитесь, что база данных электронных адресов актуальна.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-p116">Any email alias in your database that creates a bounce-back is unnecessary and puts your outbound emails at risk for further scrutiny by email filtering services. Ensure that your email database is up-to-date.</span></span>
