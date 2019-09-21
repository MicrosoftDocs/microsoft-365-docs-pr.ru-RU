---
title: Управление списками надежных отправителей при массовой рассылке почты
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d48db4a3-9fbe-45e2-bbaa-1017ffdf96f8
ms.collection:
- M365-security-compliance
description: При использовании списков надежных отправителей следует учитывать, что обработка в службе Exchange Online Protection (EOP) и программе Outlook несколько отличается. Служба рассматривает надежных отправителей и домены, проверяя RFC-адреса 5321.MailFrom и 5322.From, в то время как программа Outlook добавляет RFC-адрес 5322.From в список надежных отправителей пользователя. (Примечание. Для заблокированных пользователей и доменов служба проверяет адреса 5321.MailFrom и 5322.From.)
ms.openlocfilehash: f73cc3fc88318c4f625bf5579f73d92625624fd5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37091313"
---
# <a name="manage-safe-sender-lists-for-bulk-mailers"></a><span data-ttu-id="a8fe8-105">Управление списками надежных отправителей при массовой рассылке почты</span><span class="sxs-lookup"><span data-stu-id="a8fe8-105">Manage safe sender lists for bulk mailers</span></span>

<span data-ttu-id="a8fe8-106">Если вы хотите использовать списки надежных отправителей, необходимо знать, что служба Exchange Online Protection (EOP) и обработка Outlook работают по-другому.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-106">If you want to use safe sender lists, you should know that Exchange Online Protection (EOP) and Outlook handle processing differently.</span></span> <span data-ttu-id="a8fe8-107">Служба Office 365 учитывает надежные отправители и домены, проверяя адрес RFC 5321. MailFrom и адрес RFC 5322. from, в то время как Outlook добавляет документ RFC 5322. from Address в список надежных отправителей пользователя.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-107">The Office 365 service respects safe senders and domains by inspecting the RFC 5321.MailFrom address and the RFC 5322.From address, while Outlook adds the RFC 5322.From address to a user's safe sender list.</span></span> <span data-ttu-id="a8fe8-108">(Примечание. служба проверяет адрес 5321. MailFrom и адрес 5322. from для заблокированных отправителей и доменов.)</span><span class="sxs-lookup"><span data-stu-id="a8fe8-108">(Note: The service inspects both the 5321.MailFrom address and 5322.From address for blocked senders and domains.)</span></span>
  
<span data-ttu-id="a8fe8-p103">SMTP-адрес MAIL FROM (он же  RFC-адрес 5321.MailFrom)  это адрес электронной почты, который используется для выполнения проверок инфраструктуры политики отправителей. Он также выступает в роли пути, по которому доставляется сообщение о недоставке, если не удается доставить почту. Этот адрес электронной почты вставляется в Return-Path в заголовках сообщений по умолчанию, хотя отправитель может указать другой адрес Return-Path.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-p103">The SMTP MAIL FROM address, otherwise known as the RFC 5321.MailFrom address, is the email address that's used to perform SPF checks, and if the mail can't be delivered, the path to which the bounced message is delivered. It's this email address that is placed into the Return-Path in the message headers by default, though it's possible for the sender to designate a different Return-Path address.</span></span>
  
<span data-ttu-id="a8fe8-111">Адрес "От:" в заголовках сообщений (он же  RFC-адрес 5322.From)  это адрес электронной почты, который отображается в почтовом клиенте, например Outlook.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-111">The From: address in the message headers, otherwise known as the RFC 5322.From address, is the email address that is displayed in the mail client such as Outlook.</span></span>
  
<span data-ttu-id="a8fe8-p104">Чаще всего адреса 5321.MailFrom и 5322.From совпадают, обычно в случае взаимодействия между пользователями. Но при отправке сообщений от чужого имени эти адреса чаще всего различаются. Это характерно для массовой рассылки сообщений.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-p104">Much of the time, the 5321.MailFrom and 5322.From addresses are the same. This is typical for person-to-person communication. However, when email is sent on behalf of someone else, the addresses are frequently different. This usually happens most often for bulk email messages.</span></span>
  
<span data-ttu-id="a8fe8-116">Например, предположим, что авиалиния Blue Yonder Airlines наняла компанию Margie's Travel для отправки рекламных сообщений по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-116">For example, suppose that the airline Blue Yonder Airlines has contracted out Margie's Travel to send out its email advertising.</span></span> <span data-ttu-id="a8fe8-117">Затем в вашу папку "Входящие" приходит сообщение от отправителя blueyonder@news.blueyonderairlines.com.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-117">You then get a message in your inbox from sender blueyonder@news.blueyonderairlines.com.</span></span> <span data-ttu-id="a8fe8-118">В этом случае 5321. MailFrom Address — blueyonder.airlines@margiestravel.com, а blueyonder@news.blueyonderairlines.com — это 5322. from, который является адресом, который вы видите в Outlook.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-118">In this case, 5321.MailFrom address is blueyonder.airlines@margiestravel.com, and blueyonder@news.blueyonderairlines.com is the 5322.From address which is the one, you see in Outlook.</span></span> <span data-ttu-id="a8fe8-119">Так как служба учитывает адрес RFC 5322. from, чтобы сообщение не было отфильтровано, можно добавить адрес RFC 5322. from в качестве надежного отправителя в Outlook (как пользователь) или, если администратор настроил правило Mailflow, как показано на странице " [Защита от нежелательной почты". ](anti-spam-protection.md)Раздел "Защита".</span><span class="sxs-lookup"><span data-stu-id="a8fe8-119">Because the service respects the RFC 5322.From address, to prevent this message from getting filtered, you can add the RFC 5322.From address as a safe sender in Outlook (as a user) or, if you're an administrator set up a mailflow rule as shown on the [Anti-spam Protection](anti-spam-protection.md) section.</span></span>
  

