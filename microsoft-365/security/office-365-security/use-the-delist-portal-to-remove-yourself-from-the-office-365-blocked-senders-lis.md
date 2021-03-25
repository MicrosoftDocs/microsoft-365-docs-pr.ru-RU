---
title: Удалите себя из списка заблокированных отправителей
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/18/2016
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: В этой статье вы узнаете, как использовать портал делистингов, чтобы удалить себя из списка заблокированных отправителей Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c4488f5e5607d71da35b2921e863fb02195467e2
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206077"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="3583c-103">Удаление себя из списка заблокированных отправителей с помощью портала удаления из списка</span><span class="sxs-lookup"><span data-stu-id="3583c-103">Use the delist portal to remove yourself from the blocked senders list</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3583c-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="3583c-104">**Applies to**</span></span>
- [<span data-ttu-id="3583c-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="3583c-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="3583c-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="3583c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="3583c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3583c-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="3583c-108">Вы получаете сообщение об ошибке при попытке отправить сообщение электронной почты получателю, адрес электронной почты которого находится в Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="3583c-108">Are you getting an error message when you try to send an email to a recipient whose email address is in Microsoft 365?</span></span> <span data-ttu-id="3583c-109">Если вы считаете, что не следует получать сообщение об ошибке, можно использовать портал делистингов, чтобы удалить себя из списка заблокированных отправителей.</span><span class="sxs-lookup"><span data-stu-id="3583c-109">If you think you should not be receiving the error message, you can use the delist portal to remove yourself from the blocked senders list.</span></span>

## <a name="what-is-the-blocked-senders-list"></a><span data-ttu-id="3583c-110">Что такое список заблокированных отправителей?</span><span class="sxs-lookup"><span data-stu-id="3583c-110">What is the blocked senders list?</span></span>

<span data-ttu-id="3583c-111">Майкрософт использует этот список, чтобы защитить своих клиентов от спама, спуфинга и фишинг-атак.</span><span class="sxs-lookup"><span data-stu-id="3583c-111">Microsoft uses the blocked senders list to protect its customers from spam, spoofing, and phishing attacks.</span></span> <span data-ttu-id="3583c-112">IP-адрес вашего почтового сервера, то есть адрес, который ваш почтовый сервер использует для идентификации в Интернете, был помечен как потенциальная угроза Для Microsoft 365 по одной из различных причин.</span><span class="sxs-lookup"><span data-stu-id="3583c-112">Your mail server's IP address, that is, the address your mail server uses to identify itself on the Internet, was tagged as a potential threat to Microsoft 365 for one of a variety of reasons.</span></span> <span data-ttu-id="3583c-113">Когда Microsoft 365 добавляет IP-адрес в список, это препятствует дальнейшему общению между IP-адресом и любым из наших клиентов через наши центра обработки данных.</span><span class="sxs-lookup"><span data-stu-id="3583c-113">When Microsoft 365 adds the IP address to the list, it prevents all further communication between the IP address and any of our customers through our datacenters.</span></span>

<span data-ttu-id="3583c-114">Если ваш адрес внесен в список заблокированных отправителей, то в ответ на отправленное письмо вы получаете сообщение об ошибке примерно следующего вида:</span><span class="sxs-lookup"><span data-stu-id="3583c-114">You will know you have been added to the list when you receive a response to a mail message that includes an error that looks something like this:</span></span>

> <span data-ttu-id="3583c-115">550 5.7.606-649 Доступ запрещен, запрещена отправка _IP [IP-адрес];_ Чтобы запросить удаление из этого списка, посетите <https://sender.office.com/> и следуйте указаниям.</span><span class="sxs-lookup"><span data-stu-id="3583c-115">550 5.7.606-649 Access denied, banned sending IP [_IP address_]; To request removal from this list please visit <https://sender.office.com/> and follow the directions.</span></span> <span data-ttu-id="3583c-116">Дополнительные сведения см. в сообщении о невывозе сообщений электронной [почты в Exchange Online.](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)</span><span class="sxs-lookup"><span data-stu-id="3583c-116">For more information see [Email non-delivery reports in Exchange Online](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span></span>

<span data-ttu-id="3583c-117">где  _IP address_  IP-адрес компьютера, на котором запущен почтовый сервер.</span><span class="sxs-lookup"><span data-stu-id="3583c-117">where  _IP address_ is the IP address of the computer on which the mail server runs.</span></span>

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="3583c-118">Использование портала делистингов для удаления себя из списка заблокированных отправителей</span><span class="sxs-lookup"><span data-stu-id="3583c-118">To use delist portal to remove yourself from the blocked senders list</span></span>

1. <span data-ttu-id="3583c-119">В веб-браузере перейдите по адресу <https://sender.office.com></span><span class="sxs-lookup"><span data-stu-id="3583c-119">In a web browser, go to <https://sender.office.com>.</span></span>

2. <span data-ttu-id="3583c-p104">и следуйте инструкциям на странице. Убедитесь, что указали тот адрес электронной почты, на который пришло сообщение об ошибке, и введите указанный в нем IP-адрес. За одно посещение можно указать только один адрес электронной почты и IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="3583c-p104">Follow the instructions on the page. Ensure that you use the email address to which the error message was sent, and the IP address that is specified in the error message. You can only enter one email address and one IP address per visit.</span></span>

3. <span data-ttu-id="3583c-123">Нажмите кнопку **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="3583c-123">Click **Submit**.</span></span>

    <span data-ttu-id="3583c-124">Портал отправляет сообщение электронной почты на адрес электронной почты, который вы поставляете.</span><span class="sxs-lookup"><span data-stu-id="3583c-124">The portal sends an email to the email address that you supply.</span></span> <span data-ttu-id="3583c-125">Сообщение будет выглядеть так: снимок экрана электронной почты, полученный при отправке запроса на ![ портале делистингов.](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span><span class="sxs-lookup"><span data-stu-id="3583c-125">The email will look something like the following: ![Screenshot of email received when you submit a request through the delist portal](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span></span>

4. <span data-ttu-id="3583c-126">В полученном письме нажмите ссылку подтверждения.</span><span class="sxs-lookup"><span data-stu-id="3583c-126">Click the confirmation link in the email sent to you by the delisting portal.</span></span>

    <span data-ttu-id="3583c-127">Вы вернетесь на портал удаления из списка.</span><span class="sxs-lookup"><span data-stu-id="3583c-127">This brings you back to the delist portal.</span></span>

5. <span data-ttu-id="3583c-128">Здесь выберите **Удалить IP-адрес из списка**.</span><span class="sxs-lookup"><span data-stu-id="3583c-128">In the delist portal, click **Delist IP**.</span></span>

    <span data-ttu-id="3583c-129">После удаления IP-адреса из списка заблокированных отправителей сообщения электронной почты с этого IP-адреса будут доставляться получателям, которые используют Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3583c-129">After the IP address is removed from the blocked senders list, email messages from that IP address will be delivered to recipients who use Microsoft 365.</span></span> <span data-ttu-id="3583c-130">Поэтому убедитесь, что электронная почта, отправленная с этого IP-адреса, не будет оскорбительной или вредоносной; в противном случае IP-адрес может быть снова заблокирован.</span><span class="sxs-lookup"><span data-stu-id="3583c-130">So, make sure you're confident that email sent from that IP address won't be abusive or malicious; otherwise, the IP address might be blocked again.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3583c-131">Это может занять до 24 часов или результаты могут сильно отличаться до удаления ограничений.</span><span class="sxs-lookup"><span data-stu-id="3583c-131">It may take up to 24 hours or results can vary widely before restrictions are removed.</span></span>

<span data-ttu-id="3583c-132">См. статью Создание списков безопасного отправитель [в EOP](create-safe-sender-lists-in-office-365.md) и исходящие нежелательной почты в [EOP,](outbound-spam-controls.md) чтобы предотвратить блокировку IP.</span><span class="sxs-lookup"><span data-stu-id="3583c-132">See [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md) and [Outbound spam protection in EOP](outbound-spam-controls.md) to prevent an IP from being blocked.</span></span>