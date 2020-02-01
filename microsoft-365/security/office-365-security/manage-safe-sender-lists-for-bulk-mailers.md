---
title: Управление списками надежных отправителей при массовой рассылке почты
f1.keywords:
- NOCSH
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
ms.openlocfilehash: aaede7cab2e640603c20804f4015e19f61b6c2f3
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598946"
---
# <a name="manage-safe-sender-lists-for-bulk-mailers"></a><span data-ttu-id="a01a9-105">Управление списками надежных отправителей при массовой рассылке почты</span><span class="sxs-lookup"><span data-stu-id="a01a9-105">Manage safe sender lists for bulk mailers</span></span>

<span data-ttu-id="a01a9-106">Если вы хотите использовать списки надежных отправителей, необходимо знать, что служба Exchange Online Protection (EOP) и обработка Outlook работают по-другому.</span><span class="sxs-lookup"><span data-stu-id="a01a9-106">If you want to use safe sender lists, you should know that Exchange Online Protection (EOP) and Outlook handle processing differently.</span></span> <span data-ttu-id="a01a9-107">Служба Office 365 учитывает надежные отправители и домены, проверяя `RFC 5321.MailFrom` адрес и `RFC 5322.From` адрес, в то время как Outlook добавляет `RFC 5322.From` адрес в список надежных отправителей пользователя.</span><span class="sxs-lookup"><span data-stu-id="a01a9-107">The Office 365 service respects safe senders and domains by inspecting the `RFC 5321.MailFrom` address and the `RFC 5322.From` address, while Outlook adds the `RFC 5322.From` address to a user's safe sender list.</span></span> <span data-ttu-id="a01a9-108">(Примечание: служба проверяет `5321.MailFrom` адрес и `5322.From` адрес для заблокированных отправителей и доменов.)</span><span class="sxs-lookup"><span data-stu-id="a01a9-108">(Note: The service inspects both the `5321.MailFrom` address and `5322.From` address for blocked senders and domains.)</span></span>

<span data-ttu-id="a01a9-109">`SMTP MAIL FROM` Адрес электронной почты, который в противном случае называется `RFC 5321.MailFrom address`адресом электронной почты, используется для проверки SPF, а если не удается доставить почту, то путь, на который доставляется сообщение.</span><span class="sxs-lookup"><span data-stu-id="a01a9-109">The `SMTP MAIL FROM` address, otherwise known as the `RFC 5321.MailFrom address`, is the email address that's used to perform SPF checks, and if the mail can't be delivered, the path to which the bounced message is delivered.</span></span> <span data-ttu-id="a01a9-110">Это адрес электронной почты, который помещается `Return-Path` в заголовки сообщений по умолчанию, несмотря на то, что отправителю можно назначить другой `Return-Path` адрес.</span><span class="sxs-lookup"><span data-stu-id="a01a9-110">It's this email address that is placed into the `Return-Path` in the message headers by default, though it's possible for the sender to designate a different `Return-Path` address.</span></span>

<span data-ttu-id="a01a9-111">`From:` Адрес в заголовках сообщений, иначе называемый `RFC 5322.From` адресом, это адрес электронной почты, который отображается в почтовом клиенте, например Outlook.</span><span class="sxs-lookup"><span data-stu-id="a01a9-111">The `From:` address in the message headers, otherwise known as the `RFC 5322.From` address, is the email address that is displayed in the mail client such as Outlook.</span></span>

<span data-ttu-id="a01a9-112">В большинстве раз адреса `5321.MailFrom` и `5322.From` адреса совпадают.</span><span class="sxs-lookup"><span data-stu-id="a01a9-112">Much of the time, the `5321.MailFrom` and `5322.From` addresses are the same.</span></span> <span data-ttu-id="a01a9-113">Это типично для обмена данными между пользователями.</span><span class="sxs-lookup"><span data-stu-id="a01a9-113">This is typical for person-to-person communication.</span></span> <span data-ttu-id="a01a9-114">Однако при отправке сообщения электронной почты от имени другого пользователя адреса часто отличаются.</span><span class="sxs-lookup"><span data-stu-id="a01a9-114">However, when email is sent on behalf of someone else, the addresses are frequently different.</span></span> <span data-ttu-id="a01a9-115">Обычно это происходит чаще всего для массовых сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a01a9-115">This usually happens most often for bulk email messages.</span></span>

<span data-ttu-id="a01a9-116">Например, предположим, что Синий Yonder Airlines нанимается в командировке Марго, чтобы отправить рекламу в электронном письме.</span><span class="sxs-lookup"><span data-stu-id="a01a9-116">For example, suppose that Blue Yonder Airlines has hired Margie's Travel to send out its email advertising.</span></span> <span data-ttu-id="a01a9-117">Затем в вашу папку "Входящие" приходит сообщение от отправителя blueyonder@news.blueyonderairlines.com.</span><span class="sxs-lookup"><span data-stu-id="a01a9-117">You then get a message in your inbox from sender blueyonder@news.blueyonderairlines.com.</span></span> <span data-ttu-id="a01a9-118">В этом примере:</span><span class="sxs-lookup"><span data-stu-id="a01a9-118">In this example:</span></span>

- <span data-ttu-id="a01a9-119">`5321.MailFrom` Адрес — blueyonder.Airlines@margiestravel.com.</span><span class="sxs-lookup"><span data-stu-id="a01a9-119">The `5321.MailFrom` address is blueyonder.airlines@margiestravel.com.</span></span>

- <span data-ttu-id="a01a9-120">`5322.From` Адрес — blueyonder@news.blueyonderairlines.com, который вы увидите в Outlook.</span><span class="sxs-lookup"><span data-stu-id="a01a9-120">The `5322.From` address is blueyonder@news.blueyonderairlines.com, which is what you'll see in Outlook.</span></span>

<span data-ttu-id="a01a9-121">Чтобы предотвратить фильтрацию этого сообщения, можно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="a01a9-121">To prevent this message from being filtered, you can:</span></span>

- <span data-ttu-id="a01a9-122">**Как пользователь**: добавьте `RFC 5322.From` адрес в качестве надежного отправителя в Outlook.</span><span class="sxs-lookup"><span data-stu-id="a01a9-122">**As a user**: Add the `RFC 5322.From` address as a Safe Sender in Outlook.</span></span>

- <span data-ttu-id="a01a9-123">**Администратор**: Настройка правила для обработки [почтового ящика](anti-spam-protection.md#beyond-the-basics-more-ways-to-prevent-spam-in-office-365) (также называемого правилом транспорта).</span><span class="sxs-lookup"><span data-stu-id="a01a9-123">**As an admin**: Set up a [mail flow rule](anti-spam-protection.md#beyond-the-basics-more-ways-to-prevent-spam-in-office-365) (also known as a transport rule).</span></span>
