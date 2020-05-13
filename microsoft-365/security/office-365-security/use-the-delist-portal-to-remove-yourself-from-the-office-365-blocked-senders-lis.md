---
title: Удаление себя из списка заблокированных отправителей
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/18/2016
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: В этой статье рассказывается, как использовать портал удаления списков для удаления себя из списка заблокированных отправителей Microsoft 365.
ms.openlocfilehash: 239d30fec4d904af353731974435d377801be6c7
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208541"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="70117-103">Удаление себя из списка заблокированных отправителей с помощью портала удаления из списка</span><span class="sxs-lookup"><span data-stu-id="70117-103">Use the delist portal to remove yourself from the blocked senders list</span></span>

<span data-ttu-id="70117-104">Вы получаете сообщение об ошибке при попытке отправить сообщение электронной почты получателю, адрес которого находится в Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="70117-104">Are you getting an error message when you try to send an email to a recipient whose email address is in Microsoft 365?</span></span> <span data-ttu-id="70117-105">Если вы считаете, что не хотите получать сообщение об ошибке, можно удалить себя из списка заблокированных отправителей с помощью портала удаления списков.</span><span class="sxs-lookup"><span data-stu-id="70117-105">If you think you should not be receiving the error message, you can use the delist portal to remove yourself from the blocked senders list.</span></span>

## <a name="what-is-the-blocked-senders-list"></a><span data-ttu-id="70117-106">Что такое список заблокированных отправителей?</span><span class="sxs-lookup"><span data-stu-id="70117-106">What is the blocked senders list?</span></span>

<span data-ttu-id="70117-107">Майкрософт использует этот список, чтобы защитить своих клиентов от спама, спуфинга и фишинг-атак.</span><span class="sxs-lookup"><span data-stu-id="70117-107">Microsoft uses the blocked senders list to protect its customers from spam, spoofing, and phishing attacks.</span></span> <span data-ttu-id="70117-108">IP-адрес почтового сервера, то есть адрес, который почтовый сервер использует для идентификации в Интернете, был отмечен как потенциальную угрозу для Microsoft 365 по одной из различных причин.</span><span class="sxs-lookup"><span data-stu-id="70117-108">Your mail server's IP address, that is, the address your mail server uses to identify itself on the Internet, was tagged as a potential threat to Microsoft 365 for one of a variety of reasons.</span></span> <span data-ttu-id="70117-109">Когда Microsoft 365 добавляет IP-адрес в список, он предотвращает все дальнейшие связи между IP-адресом и любыми клиентами через центры обработки данных.</span><span class="sxs-lookup"><span data-stu-id="70117-109">When Microsoft 365 adds the IP address to the list, it prevents all further communication between the IP address and any of our customers through our datacenters.</span></span>

<span data-ttu-id="70117-110">Если ваш адрес внесен в список заблокированных отправителей, то в ответ на отправленное письмо вы получаете сообщение об ошибке примерно следующего вида:</span><span class="sxs-lookup"><span data-stu-id="70117-110">You will know you have been added to the list when you receive a response to a mail message that includes an error that looks something like this:</span></span>

> <span data-ttu-id="70117-111">550 5.7.606-649 доступ запрещен, запрещена отправка IP [_IP-адрес_]; Чтобы запросить удаление из этого списка, перейдите https://sender.office.com/ к ним и следуйте инструкциям.</span><span class="sxs-lookup"><span data-stu-id="70117-111">550 5.7.606-649 Access denied, banned sending IP [_IP address_]; To request removal from this list please visit https://sender.office.com/ and follow the directions.</span></span> <span data-ttu-id="70117-112">Дополнительные сведения см. [в статье Exchange Online Reports не о доставке](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="70117-112">For more information see [Email non-delivery reports in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span></span>

<span data-ttu-id="70117-113">где  _IP address_  IP-адрес компьютера, на котором запущен почтовый сервер.</span><span class="sxs-lookup"><span data-stu-id="70117-113">where  _IP address_ is the IP address of the computer on which the mail server runs.</span></span>

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="70117-114">Удаление себя из списка заблокированных отправителей с помощью портала удаления из списка</span><span class="sxs-lookup"><span data-stu-id="70117-114">To use delist portal to remove yourself from the blocked senders list</span></span>

1. <span data-ttu-id="70117-115">В веб-браузере перейдите по адресу [https://sender.office.com](https://sender.office.com)</span><span class="sxs-lookup"><span data-stu-id="70117-115">In a web browser, go to [https://sender.office.com](https://sender.office.com).</span></span>

2. <span data-ttu-id="70117-p104">и следуйте инструкциям на странице. Убедитесь, что указали тот адрес электронной почты, на который пришло сообщение об ошибке, и введите указанный в нем IP-адрес. За одно посещение можно указать только один адрес электронной почты и IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="70117-p104">Follow the instructions on the page. Ensure that you use the email address to which the error message was sent, and the IP address that is specified in the error message. You can only enter one email address and one IP address per visit.</span></span>

3. <span data-ttu-id="70117-119">Нажмите кнопку **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="70117-119">Click **Submit**.</span></span>

    <span data-ttu-id="70117-120">Портал отправляет электронное сообщение на адрес электронной почты, который вы указали.</span><span class="sxs-lookup"><span data-stu-id="70117-120">The portal sends an email to the email address that you supply.</span></span> <span data-ttu-id="70117-121">Сообщение электронной почты будет выглядеть примерно так: ![ снимок экрана, полученный при отсылке запроса через портал рассписка](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span><span class="sxs-lookup"><span data-stu-id="70117-121">The email will look something like the following: ![Screenshot of email received when you submit a request through the delist portal](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span></span>

4. <span data-ttu-id="70117-122">В полученном письме нажмите ссылку подтверждения.</span><span class="sxs-lookup"><span data-stu-id="70117-122">Click the confirmation link in the email sent to you by the delisting portal.</span></span>

    <span data-ttu-id="70117-123">Вы вернетесь на портал удаления из списка.</span><span class="sxs-lookup"><span data-stu-id="70117-123">This brings you back to the delist portal.</span></span>

5. <span data-ttu-id="70117-124">Здесь выберите **Удалить IP-адрес из списка**.</span><span class="sxs-lookup"><span data-stu-id="70117-124">In the delist portal, click **Delist IP**.</span></span>

    <span data-ttu-id="70117-125">После удаления IP-адреса из списка заблокированных отправителей сообщения электронной почты с этого IP-адреса будут доставляться получателям, которые используют Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="70117-125">After the IP address is removed from the blocked senders list, email messages from that IP address will be delivered to recipients who use Microsoft 365.</span></span> <span data-ttu-id="70117-126">Поэтому убедитесь, что вы уверены, что электронная почта, отправленная с этого IP-адреса, не будет содержать нарушения или вредоносных программ; в противном случае IP-адрес может быть заблокирован повторно.</span><span class="sxs-lookup"><span data-stu-id="70117-126">So, make sure you're confident that email sent from that IP address won't be abusive or malicious; otherwise, the IP address might be blocked again.</span></span>

    > [!NOTE]
    > <span data-ttu-id="70117-127">Может потребоваться до 24 часов, а результаты могут сильно различаться до удаления ограничений.</span><span class="sxs-lookup"><span data-stu-id="70117-127">It may take up to 24 hours or results can vary widely before restrictions are removed.</span></span>

<span data-ttu-id="70117-128">В разделе [Создание списков надежных отправителей в EOP](create-safe-sender-lists-in-office-365.md) и [исходящих сообщениях защиты от нежелательной почты в EOP](outbound-spam-controls.md) , чтобы запретить отправку IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="70117-128">See [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md) and [Outbound spam protection in EOP](outbound-spam-controls.md) to prevent IP from being blacklisted.</span></span>
